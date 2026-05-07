# AOSP design patterns

Lawnchair is an architectural hybrid. Because it is a fork of AOSP Launcher3, the codebase is divided into two distinct zones that follow different rules.

This page documents the design patterns governing the **AOSP Zone**, which primarily includes all components outside the `lawnchair` module, including `src` and `quickstep` .

If you are working in these areas, you are working on a system-level platform component. You must prioritize stability, performance, and resource management over modern application convenience.

### UI thread responsiveness

The main thread (UI thread) is responsible for drawing the interface and responding to touch input. In a launcher, even a minor delay on this thread results in dropped frames and a jarring user experience.

**Tips**

* Never perform disk I/O, network requests, or complex computations on the main thread.
* Offload heavy tasks to background threads using internal system executors or handlers.
* Update the UI only on the main thread using `Handler(Looper.getMainLooper())`.

**Example:**

```java
// Offloading search logic to a background thread
public void onSearchQueryChanged(String query) {
    MODEL_EXECUTOR.execute(() -> {
        List<SearchResult> results = performHeavySearch(query);
        MAIN_EXECUTOR.execute(() -> updateSearchUI(results));
    });
}
```

### Ephemeral and dynamic state

System state (locale, theme, orientation, or user profiles) can change at any time. Android aggressively manages resources and may kill processes that are not in the foreground.

**Tips**

* Never assume state is static or persists across process death.
* Implement robust invalidation strategies for all caches (e.g., icon caches or search result caches).
* React gracefully to `onConfigurationChanged` and system state broadcasts.

**Example:**

```java
// Invalidating cache when system theme or locale changes
public void onSystemStateChanged(Context context) {
    String currentKey = generateStateKey(context);
    if (!currentKey.equals(mLastKnownKey)) {
        mIconCache.evictAll();
        mLastKnownKey = currentKey;
    }
}
```

### Resource and memory constraints

The launcher is a persistent process. Every object allocation and memory footprint must be justified. Large allocations trigger the Low Memory Killer (LMK), which can terminate the launcher.

**Tips**

* Avoid unnecessary object allocations in performance-critical paths (e.g., `onDraw`, `onLayout`, or `onScroll`).
* Prefer primitives or light data structures like `SparseArray` over heavy collections like `HashMap` where appropriate.
* Recycle views and bitmaps whenever possible.

**Example:**

```java
// Using bitwise flags instead of object-heavy collections
public static final int FLAG_ROUNDED_CORNERS = 1 << 0;
public static final int FLAG_DROP_SHADOW = 1 << 1;

public void drawView(Canvas canvas, int flags) {
    if ((flags & FLAG_ROUNDED_CORNERS) != 0) {
        // apply drawing logic
    }
}
```

### API stability and compatibility

The launcher must support a wide range of API levels and potentially broken OEM implementations.

**Tips**

* Use runtime checks (`Build.VERSION.SDK_INT`) to guard features using newer APIs.
* Use compatibility wrappers to provide fallbacks for older Android versions.
* Maintain backwards compatibility for core launcher features.

**Example:**

```java
public void setBlurEffect(View view) {
    if (Build.VERSION.SDK_INT >= Build.VERSION_CODES.S) {
        view.setRenderEffect(RenderEffect.createBlurEffect(...));
    } else {
        // Fallback or no-op
    }
}
```

### Decoupling via interfaces and abstractions

Deeply coupled code is difficult to test, extend, or modify without causing cascading failures across the system.

**Tips**

* Define clear boundaries between subsystems using interfaces or abstract classes.
* Inject dependencies rather than instantiating them directly.
* Allow implementations to be swapped based on device profiles or configuration.

**Example:**

```java
// Defining a contract for search providers
public interface SearchProvider {
    void fetchResults(String query, Callback callback);
}

// Consuming the interface without knowing the concrete implementation
public class SearchController {
    private final SearchProvider mProvider;
    public SearchController(SearchProvider provider) {
        this.mProvider = provider;
    }
}
```

### Granular security and permissions

Actions impacting user privacy or device integrity must be protected. The system enforces a least-privilege principle.

**Tips**

* Perform explicit permission checks before accessing sensitive data (e.g., contacts or notification data).
* Handle the absence of permissions gracefully without crashing.

**Example:**

```java
public void loadContacts(Context context) {
    if (context.checkSelfPermission(Manifest.permission.READ_CONTACTS) != PackageManager.PERMISSION_GRANTED) {
        return; // Handle gracefully
    }
    // Proceed with loading contacts
}
```

### Designed-in extensibility

As an AOSP fork, Lawnchair must be able to modify behavior without forking the entire codebase or losing the ability to upstream changes.

**Tips**

* Utilize provided AOSP extension points and hooks.
* Design new features with a "pluggable" mindset.
* Use resource overlays or build configurations to swap behaviors.

### Pervasive diagnostics and logging

Diagnosing issues in a complex, system-integrated app across millions of devices is difficult without detailed context.

**Tips**

* Use `Log.d` and `Log.v` for internal debugging, but guard them with `Log.isLoggable` checks.
* Utilize `android.os.Trace` for performance profiling.
* Provide enough context in error logs to understand the state of the system at the time of failure.

### **Immutability for predictability**

Shared mutable state is a major source of race conditions and unpredictable behavior in a multithreaded environment.

**Tips**

* Design data-carrying objects to be immutable where possible.
* Return new instances rather than modifying existing objects in place.
* Use `final` for class fields to ensure thread safety and clarity.

### Graceful degradation

Individual component failures should not bring down the entire launcher or lock the user out of their device.

**Tips**

* Anticipate and handle common failure modes (e.g., file not found, API error).
* Provide sensible defaults or fallbacks when a specific feature fails.
* Avoid "fail-fast" logic in core UI paths.

**Example:**

```java
public Drawable loadIcon(Context context, String pkg) {
    try {
        return mPm.getApplicationIcon(pkg);
    } catch (NameNotFoundException e) {
        return mPm.getDefaultActivityIcon(); // Fallback
    }
}
```
