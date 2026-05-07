# Lawnchair design patterns

The **Lawnchair module** (everything found in `lawnchair`) represents the modern layer of the project. While the AOSP modules focuses on system-level constraints, this zone utilizes Modern Android Development (MAD) tools like Kotlin and Jetpack Compose.

However, Lawnchair follows a **pragmatic MAD** approach. Because we are bridging a modern UI with a legacy platform, we often prioritize development velocity and direct state access over strict architectural purity (such as "clean" MVVM or heavy Dependency Injection).

### **Preference-driven architecture**

Most of Lawnchair's customization is driven by a centralized preference system. This is the "brain" of the launcher.

**The Pattern:**

* **`prefs` (Legacy):** Uses `SharedPreferences` for basic types. Avoid adding new keys here.
* **`prefs2` (Modern):** Uses `Preference Datastore`. This is the preferred location for all new settings, supporting non-primitive data and default values from `config.xml`.
* The preference key is the single source of truth. The UI and the launcher logic both observe the key to ensure consistency.

### The manager pattern

Lawnchair utilizes thread-safe singletons to manage persistent subsystems that need to be accessible from both the View-based AOSP code and the Compose-based UI layer.

**The Pattern:**

* Access major subsystems (e.g., `FontCache`, `IconCache`, `LauncherAppState`) via their static `INSTANCE` or `getInstance(context)` methods.
* These managers often handle their own internal caching and state invalidation based on system changes.

### Pragmatic state management

In many modern apps, state flows from a data source through a repository to a ViewModel. In Lawnchair, we often bypass these layers to directly link the UI to our preference systems or internal registries.

Our UI structure follows a **70/20/10 complexity rule**:

* For s**imple settings**, which use standard toggles and sliders, use direct state access via `getAdapter()` in the Composable. Avoid ViewModels or extra layers.
* For more **complex screens** with localized logic, such as search filters or file picking, use `remember`, `derivedStateOf`, and `produceState` within the Composable.
* Screens that mix multiple data sources or remote APIs must follow a full MVVM pattern using `AndroidViewModel` and `StateFlow` to ensure the code remains readable.

**Tips**

* Use `getAdapter()` to bridge persistent storage and the UI. This provides a `PreferenceAdapter` that handles state updates and writes automatically.
* Avoid creating ViewModels for simple settings screens. Use localized state or direct preference access instead.
* Utilize `preferenceManager2()` and `preferenceManager()` top-level functions within Compose to access data.

**Example:**

```kotlin
@Composable
fun SearchSettings() {
    val prefs2 = preferenceManager2()
    // Direct state access via adapter
    val showSearch = prefs2.showSearch.getAdapter()

    SwitchPreference(
        adapter = showSearch,
        label = stringResource(R.string.show_search_label)
    )
}
```

### Hybrid UI and interoperation

Lawnchair is in a state of "Compose-ification." We are incrementally migrating a View-based system to Jetpack Compose. This requires a hybrid approach where the two systems coexist and share state.

**The Pattern:**

* Use `ComposeView` within XML layouts or programmatically to host new UI components inside legacy Launcher3 areas (e.g., custom search results).
* Use `AndroidView` within Compose to host legacy components that are too complex to rewrite immediately.
* Pass state objects or callbacks across the boundary. Avoid complex reactive streams (like RxJava) across this boundary unless already present in the legacy code.

### Direct UI-coupled logic

For the majority of the project, we couple business logic and navigation directly to the UI components. This reduces the boilerplate required to manage a large number of independent settings and small features.

We only adopt strict MAD principles or MVVM if a screen is literally impossible to understand without them.

**The Pattern:**

* Pass `NavController` or state holders directly into Composable functions.
* Use `remember` and `derivedStateOf` within the UI layer to handle complex presentation logic that would traditionally live in a ViewModel.
* Directly trigger side effects (like updating system settings or restarting the launcher) from UI callbacks.

**Example:**

```kotlin
@Composable
fun ThemeSelector(navController: NavController) {
    val themeState = rememberThemeState()
    
    ThemeList(
        onThemeSelected = { theme ->
            themeState.apply(theme)
            navController.popBackStack() // Direct navigation coupling
        }
    )
}
```

### Simplified dependency injection

While we use frameworks like Dagger/Hilt in some areas, we frequently rely on singleton "Managers" and top-level `getInstance(context)` calls for core launcher components.

**The Pattern:**

* Access major subsystems (e.g., `IconCache`, `LauncherAppState`) via their static `INSTANCE` or `getInstance()` methods.
* Use `LocalContext.current` in Compose to fetch the required context for these singleton accessors.
* Prioritize simplicity and fast initialization over strict constructor injection in the UI layer.

### Code quality and testing

Lawnchair prioritizes feature availability and user-facing stability.

Currently, the project **does not utilize unit tests or automated UI tests**. Code quality is maintained through manual verification by contributors and core maintainers, alongside feedback from our community and Nightly build testers.
