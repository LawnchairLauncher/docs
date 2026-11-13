# Project overview

Lawnchair is an Android home screen launcher replacement built on top of AOSP [Launcher3][l3-codebase]. To help with navigating or contributing to the codebase, it is important to understand how Android's default launcher is architected.

## Understanding the Launcher3 foundation

AOSP Launcher3 is a tightly coupled monolithic app of a core Android system, and is designed as an extensible base launcher for what is colloquially called "vendors" to layer in vendor-specific code. Conceptually, Lawnchair and any launcher derived from Launcher3 code is a vendor implementation itself by extending, overriding and theming Launcher3 rather than rewriting a launcher from scratch.

Because Lawnchair is a vendor implementation living inside a forked AOSP tree, the repository contains two distinct layers:

1. **Launcher3** (such as `src/`, `quickstep/`): A mix of legacy Java and Kotlin, following the [AOSP Java code style][aosp-java-style], [Google Kotlin style guide and others][greater-google-code-style].
2. **Lawnchair** (`lawnchair/`): Modern Kotlin using Jetpack Compose, generally following following the Modern Android Development (MAD) practices

See [AOSP design patterns](aosp-design-patterns), [Lawnchair design patterns](lawnchair-design-patterns), and the [Glossary](glossary) for deeper dives into the codebase.

## How Lawnchair extends Launcher3

Whenever Lawnchair adds a feature that clashes with the Launcher3 layer, we try to follow a hierachy of "meddling" to keep the upstream base as clean as possible:

1. **Resource and config overlays**: Overriding XML dimensions, booleans, and class strings inside source set of the Lawnchair layer.
   Example: Overriding `taskbar_background` resources on specific APIs to fix missing resource crashes on problematic devices.
2. **Subclassing and delegates**: Extending extensible base classes and wiring them in via Launcher3 factory hooks or dagger modules.
   Example: `LawnchairLauncher` extending `QuickstepLauncher` to add in additional functionality instead of modifying `QuickstepLauncher` or `Launcher` directly
3. **Direct edits** (as a last resort): Edit part of Launcher3 code with documentation to mark what was changed, why it is needed, and what to keep in mind for during future AOSP merges.
   Example: Replacing Launcher3's allapps search function with Lawnchair's own allapps search function.

## How Lawnchair decouples Launcher3 from AOSP

Unlike any other derivatives of Launcher3, Lawnchair builds the full `Quickstep` layer while still running as a standalone app for non-root users, this had resulted in the project structure growing twice the sizes of what any other derivatives do. An notable example would be the [`platform_frameworks_libs_systemui`][platform-systemui-repo], `wmshell`, `systemUI`, `flags`, and `prebuilts` directories. These are not part of Launcher3 itself but they are internal AOSP APIs and dependencies that Launcher3 Quickstep layer uses to communicate with the rest of the Android system. Bundling them allows Lawnchair to compile outside a full AOSP build tree, and support QuickSwitch feature or which may be aptly called Lawnchair as a system Recents provider.

A known annoying quirk is that at runtime, classes provided by the host device's Android system framework may take priority over these bundled directories.

## Why this matters for contributors

On every major and minor Android release, Lawnchair may rebases or merges its tree onto the latest AOSP Launcher3 tag.

If a pull request patch reformats or converts an upstream Java class to Kotlin, or weaves 300 lines of feature logic directly into `Workspace.java`, rebasing or merging onto the next Android release becomes painfully complex. Try to keep your logic inside Lawnchair layer and treat Launcher3 layer as read-only whenever possible.

This may increase the chance of having your pull request be merged into the repository quicker.

## Code formatting and testing

Code formatting and style are enforced via [Spotless][spotless-repo] rules, and currently has no unit or automated UI tests. Contributors and maintainers verify changes manually, with additional feedback from GitHub issues and Nightly build testers.

[l3-codebase]: https://cs.android.com/android/platform/superproject/+/android-latest-release:packages/apps/Launcher3
[aosp-java-style]: https://source.android.com/docs/setup/contribute/code-style
[greater-google-code-style]: https://google.github.io/styleguide
[platform-systemui-repo]: https://github.com/LawnchairLauncher/platform_frameworks_libs_systemui
[spotless-repo]: https://github.com/diffplug/spotless
