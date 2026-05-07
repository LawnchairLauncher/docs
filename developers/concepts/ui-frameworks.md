# UI frameworks

Lawnchair utilizes a hybrid UI architecture. The project is currently undergoing a gradual migration from the View system to Jetpack Compose.

This results in a codebase where both toolkits coexist, each serving a specific purpose based on its architectural zone.

### The View system

The majority of the core launcher experience is built using the standard Android View system, and is currently used for the following areas:

* The core workspace and app drawer layout.
* UI components like Smartspace.
* Most legacy search result layouts and standard launcher popups.

When modifying these areas, maintain the existing View-based patterns to ensure compatibility with AOSP's internal recycling and animation logic.

### Jetpack Compose

[Jetpack Compose](https://developer.android.com/compose) is the modern standard for the Lawnchair module, and is the required toolkit for the following areas:

* The entire Lawnchair settings UI (Home settings).
* New custom bottom sheets and overlays.
* Modernized search result components and the About page.

Avoid using XML layouts for new features in these areas. Instead, use or create components in the `lawnchair/ui` package.

#### Interoperability and state

Because these two systems must work together, Lawnchair uses standard Android interoperability patterns to bridge the gap.

When bridging these systems, keep the interaction logic as simple as possible. Prefer passing simple data types or basic callbacks across the toolkit boundary rather than complex reactive streams.

#### When to use each toolkit

As a general rule, follow the existing toolkit used by the module you are touching.

* If you are adding a toggle or a new screen to the settings, use **Jetpack Compose**.
* If you are fixing a visual bug in the Workspace or dock, use the **View system**.
* If you are implementing a major new feature, consult with the core team to determine if the area is ready for Jetpack Compose or if View-based performance is required.
