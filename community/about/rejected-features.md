# Rejected features

To keep Lawnchair stable, performant, and maintainable for our small team, we must establish clear boundaries regarding what is in-scope for a home screen app.

This page lists frequently requested features that we have decided not to implement, along with our reasoning and recommended alternatives.

### Modifying system UI elements

Users often request settings to modify the lock screen, status bar, quick settings panel, or notification shade.

However, a launcher has absolutely no system authority over these areas. They are owned and rendered by the system's SystemUI process. Modifying them from a third-party application requires fragile workarounds, root-level hacks, or accessibility overlays that degrade performance and break easily with system updates.

We suggest using your device's built-in system customization settings, custom ROMs, or dedicated system overlay utilities (such as [SystemUI Tuner](https://github.com/zacharee/Tweaker), [Good Lock](https://play.google.com/store/apps/details?id=com.samsung.android.goodlock), or specialized customization tools) to modify these areas.

### App locking

This feature would allow users to lock individual applications with a PIN, pattern, or biometric check directly within the launcher.

However, launcher-level app locking only protects the app's icon from being tapped on the home screen, without securing anything else. A user can easily bypass this "lock" by launching the target application from the Settings app, Google Assistant, notifications, or a link from another app. Implementing this will also add significant state complexity and creates a false sense of security.

We suggest using Android's built-in [Private Space feature](https://support.google.com/android/answer/15341885) (available on Android 15 and newer) or your device manufacturer's system-level app locker, which secure the application at the OS level.

### Additional system overlays

This includes requests for persistent sidebars, floating widgets, or custom utility panels that remain visible on top of other applications.

However, managing window overlays is outside the scope of a launcher. Creating and maintaining drawing layers that display over other apps significantly increases visual bugs, compatibility issues across different Android versions, and overall project complexity.

We suggest using dedicated utility applications from the Google Play Store that are designed specifically to manage floating sidebars or overlay widgets.

### Desktop mode

This feature would adapt Lawnchair's layout into a desktop-like interface (similar to Windows or macOS) when the device is connected to an external display.

However, Android's built-in desktop mode is highly experimental, unstable, and implemented inconsistently across different device manufacturers. Launcher3's desktop code also contains additional hooks and customizations that require root access, significantly reducing the target audience for this feature.

As such, supporting this behavior would require a massive dedicated effort that could be redirected to improving Lawnchair's existing features. Furthermore, supporting desktop mode would introduce user expectations for advanced window management and customization that are far out of scope.

We suggest using your system's default desktop interface (such as Samsung DeX) if your device supports external display output.

### Built-in widgets

This includes requests for built-in, pre-designed widgets for weather, clock, calendar, or system monitoring, outside of the standard At a Glance and search bar.

However, maintaining custom widgets is a significant form of feature bloat. Designing, creating, and testing widgets, as well as adding support for many API integrations (such as weather data sources) requires constant maintenance and takes time away from improving core launcher functionality.

We suggest using dedicated third-party widget applications (such as [KWGT](https://play.google.com/store/apps/details?id=org.kustom.widget)) to design or apply highly customized clock, weather, and system widgets.

### Built-in icon packs

This includes requests to bundle custom, pre-designed icon packs directly Lawnchair.

However, icon design and app development should remain separate. Bundling static icon packs increases Lawnchair's file size unnecessarily for assets that cannot be dynamically or algorithmically updated. Our official icon pack project, Lawnicons, is already developed and distributed as a separate application for this reason.

We suggest installing third-party icon packs (including Lawnicons) instead, and applying them through [Lawnchair's icon settings](https://app.gitbook.com/s/AIacWTbuc2FAEgCbTojQ/core-features/theming-and-icons).
