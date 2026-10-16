# Rejected features

Lawnchair focuses on features that fit a home screen app and that our small team can maintain.

This page explains why we have declined certain requests and suggests alternatives.

### Modifying system UI elements

Users often ask for settings to change the lock screen, status bar, Quick Settings panel, or notification shade.

Android's SystemUI process owns and renders these areas; a launcher cannot control them. Third-party apps can only try fragile workarounds, root-level hacks, or accessibility overlays, which can hurt performance and break after system updates.

We suggest using your device's built-in system customization settings, custom ROMs, or dedicated system overlay utilities (such as [SystemUI Tuner](https://github.com/zacharee/Tweaker), [Good Lock](https://play.google.com/store/apps/details?id=com.samsung.android.goodlock), or specialized customization tools) to modify these areas.

### App locking

This feature would let users lock apps with a PIN, pattern, or biometric check through the launcher.

But a launcher-level lock only blocks access through the launcher's app icons. Users can still open the app from Settings, Google Assistant, a notification, or another app. This feature would add state complexity and give users a false sense of security.

We suggest using Android's built-in [Private Space feature](https://support.google.com/android/answer/15341885) (available on Android 15 and newer) or your device manufacturer's app locker, which secures apps at the system level.

### Additional system overlays

Requests in this category include persistent sidebars, floating widgets, and utility panels that stay on top of other apps.

Managing overlays is outside a launcher's scope. Drawing layers over other apps can cause visual bugs and compatibility problems across Android versions, while adding maintenance work.

We suggest using dedicated utility applications from the Google Play Store that are designed specifically to manage floating sidebars or overlay widgets.

### Desktop mode

This feature would give Lawnchair a desktop-like layout, similar to Windows or macOS, when connected to an external display.

Android's built-in desktop mode is experimental and varies across device manufacturers. Launcher3's desktop code also relies on hooks and customizations that require root access, limiting the number of users who could use this feature.

Supporting desktop mode would take substantial work away from Lawnchair's existing features. It would also create expectations for advanced window management and customization, which are outside the project's scope.

We suggest using your system's default desktop interface (such as Samsung DeX) if your device supports external display output.

### Built-in widgets

This includes requests for built-in weather, clock, calendar, or system-monitoring widgets beyond At a Glance and the search bar.

Custom widgets would add ongoing maintenance. Designing and testing them, along with supporting integrations such as weather data sources, would take time away from core launcher features.

We suggest using dedicated third-party widget applications (such as [KWGT](https://play.google.com/store/apps/details?id=org.kustom.widget)) to design or apply highly customized clock, weather, and system widgets.

### Built-in icon packs

This includes requests to bundle custom icon packs with Lawnchair.

Icon design and app development are separate projects. Bundled icon packs would increase Lawnchair's size, and their static assets cannot be updated dynamically. Lawnicons is distributed as a separate app for this reason.

We suggest installing third-party icon packs (including Lawnicons) instead, and applying them through [Lawnchair's icon settings](https://app.gitbook.com/s/AIacWTbuc2FAEgCbTojQ/core-features/theming-and-icons).
