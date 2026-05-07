# Project overview

This page provides a high-level overview of Lawnchair's origins and its architectural foundation. Understanding this context is required to navigate the codebase.

### Lawnchair and Launcher3

Lawnchair is a fork of [Launcher3](https://cs.android.com/android/platform/superproject/main/+/main:packages/apps/Launcher3/), the default home screen application in the Android Open Source Project (AOSP). Lawnchair is built upon the same codebase used for the stock Android launcher.

Launcher3 is designed as a core component of the Android operating system. This distinction influences its architecture:

* AOSP components prioritize stability, performance, and resource management across diverse hardware and Android versions.
* Lawnchair inherits design philosophies and legacy structures directly from AOSP. These patterns often differ from Modern Android Development (MAD) practices used in standalone applications.

#### Characteristics inherited from AOSP

Lawnchair inherits several characteristics from its AOSP foundation:

* Deep system integration for features like the Recents screen (Quickstep) and gesture navigation.
* Variable performance where core AOSP features are generally responsive, while Lawnchair-specific features or areas undergoing refactoring may not yet achieve the same level of fluidity.
* Platform-level optimizations to maintain a minimal resource footprint.
* Resilience against system-wide crashes through robust error handling.

To dive deeper into the technical principles governing the codebase, refer to [AOSP design patterns](aosp-design-patterns.md) and L[awnchair design patterns](lawnchair-design-patterns.md). You can also consult the Glossary for definitions of project-specific terminology.
