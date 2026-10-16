# Project overview

## Lawnchair and Launcher3

Lawnchair is a fork of [Launcher3](https://cs.android.com/android/platform/superproject/main/+/main:packages/apps/Launcher3/), the default home screen application in the Android Open Source Project (AOSP). Lawnchair is built upon the same codebase used for the stock Android launcher.

Launcher3 is designed as a core component of the Android operating system. This distinction influences its architecture:

* AOSP components prioritize stability, performance, and resource management across diverse hardware and Android versions.
* Lawnchair inherits design philosophies and legacy structures directly from AOSP. These patterns often differ from Modern Android Development (MAD) practices used in standalone applications.

### Characteristics inherited from AOSP

Lawnchair inherits several characteristics from its AOSP foundation:

* Deep system integration for features like the Recents screen (Quickstep) and gesture navigation.
* Core AOSP features are generally responsive; Lawnchair-specific features and areas being refactored may be less fluid.
* Platform-level optimizations to maintain a minimal resource footprint.
* Error handling that helps limit the impact of system-wide failures.

See [AOSP design patterns](aosp-design-patterns.md), [Lawnchair design patterns](lawnchair-design-patterns.md), and the [glossary](glossary.md) for more about the codebase.

### Project structure

Lawnchair is composed of multiple Gradle modules. The most important ones are listed below:

* `lawnchair`&#x20;
  * Contains Lawnchair-specific code and UI. Generally, most changes should be done here.
* `src`
  * Contains the core code of Launcher3 with modifications.
* `quickstep`
  * Contains the implementation of QuickStep, which enables Recents integration
* [`platforms/frameworks/libs/systemui`](https://github.com/LawnchairLauncher/platform_frameworks_libs_systemui)
  * Contains multiple libraries in SystemUI used by Lawnchair. See the linked repository for further information.

### Code quality and testing

Lawnchair prioritizes feature availability and user-facing stability.

The project currently has no unit or automated UI tests. Contributors and maintainers verify changes manually, with additional feedback from GitHub issues and Nightly build testers.
