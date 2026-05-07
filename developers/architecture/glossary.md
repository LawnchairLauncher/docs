# Glossary

This page defines common terms and acronyms used throughout the Launcher3 and Lawnchair codebase. Use these terms when naming variables, classes, or documenting code.

### Terminology mapping

Some terminology shown in the UI is shown differently in Launcher3's code. This is summarized in the table below:

<table><thead><tr><th width="170">UI terminology</th><th width="216">Code terminology</th></tr></thead><tbody><tr><td>Home screen</td><td>Workspace</td></tr><tr><td>Dock</td><td>Hotseat</td></tr><tr><td>App drawer</td><td>All apps</td></tr><tr><td>At a Glance</td><td>Smartspace</td></tr><tr><td>Recents screen</td><td>Overview</td></tr><tr><td>Search bar</td><td>Quick Search Bar (QSB)</td></tr><tr><td>App icon with label</td><td><code>BubbleTextView</code></td></tr></tbody></table>

### Core concepts

* **Launcher**
  * An Android app that provides the Home screen experience for a device.
* **Launcher3**
  * The default AOSP launcher codebase that Lawnchair builds on and customizes.
* **Quickstep**
  * The launcher integration layer for Recents, gesture navigation, and task transitions.
* **Home screen**
  * The main user surface containing pages of apps, widgets, and folders.
* **All Apps**
  * The app drawer surface that lists installed apps.
* **Widget**
  * A resizable app-provided view that can be placed on the Home screen.
* **Shortcut**
  * A launchable item representing an app entry point or deep link.
* **Deep shortcut**
  * A shortcut exposed by an app for a specific in-app action.

### Launcher UI surfaces

* `Workspace`
  * The paged container that holds the home screen content.
* `Hotseat`
  * The fixed dock area used for frequently accessed apps.
* `CellLayout`
  * The grid layout for a single Workspace page.
* `PagedView`
  * The base horizontally paged view used by Workspace and related surfaces.
* `AllAppsContainerView`
  * The root container responsible for presenting the All Apps UI.
* `BubbleTextView`
  * The icon-and-label view used for app and shortcut items.
* **Folder**
  * A container item that groups multiple app or shortcut items.
* `FolderIcon`
  * The Home screen representation of a Folder.
* **Folder open state**
  * The transient UI state where folder contents are shown in an overlay.
* `DragLayer`
  * The top-level overlay layer used during drag and floating UI operations.
* `AbstractFloatingView`
  * Base class for floating surfaces like open folders and popups.

### Data model

* `ItemInfo`
  * Base model type for items shown by the launcher.
* `WorkspaceItemInfo`
  * Model for app and shortcut items placed on the Workspace or Hotseat.
* `AppInfo`
  * Model representing an installed application entry in All Apps.
* `FolderInfo`
  * Model for folder metadata and its contained items.
* `LauncherAppWidgetInfo`
  * Model for widgets placed on the Workspace.
* `BgDataModel`
  * In-memory store for Workspace, Hotseat, and folder data.
* `AllAppsList`
  * In-memory list of app entries used to build All Apps.
* `LauncherModel`
  * Coordinator that loads launcher data and binds it to UI callbacks.
* `LoaderTask`
  * Background task that reads and builds launcher model data.
* `ModelCallbacks`
  * Callback contract used to bind model updates to UI surfaces.
* `PendingAddItemInfo`
  * Temporary model used while adding a new item before final placement.

### Launcher UI state

* `LauncherState`
  * A named UI mode such as `NORMAL`, `ALL_APPS`, or `OVERVIEW`.
* `StateManager`
  * Component that transitions between LauncherState values and animations.
* `NORMAL` **state**
  * Default launcher state showing the Home screen.
* `ALL_APPS` **state**
  * State where the app drawer is the primary visible surface.
* `OVERVIEW` **state**
  * State where recent tasks are shown for switching.
* `SPRING_LOADED` **state**
  * Temporary drag-focused state used during Workspace edits and rearrangement.
* `StateHandler`
  * Interface for components that apply per-state visual and behavioral changes.

### Drag and placement state

* `DragController`
  * Controller that owns drag lifecycle events from start to drop.
* `DragSource`
  * Interface for a component that initiates a drag operation.
* `DropTarget`
  * Interface for a component that can accept dropped items.
* `DragObject`
  * Runtime object carrying drag data, drag view, and coordinates.
* `DragView`
  * Floating visual copy of the dragged item shown during drag.
* `Pre-drag`
  * Early long-press phase before a full drag session begins.
* `GridOccupancy`
  * Internal grid map used to track filled and free cells.
* **Reorder**
  * Item movement logic that shifts neighbors to satisfy a drop placement.

### Device layout profile

* **Device Profile**
  * Runtime profile containing size, orientation, and layout measurements.
* **IDP (Invariant Device Profile)**
  * Base profile used without activity context to define core grid metrics.
* **Grid size**
  * The row and column configuration used for Workspace item placement.
* **Window bounds**
  * The available screen region used for layout calculations.
* **Responsive layout**
  * Layout behavior that adapts dimensions and spacing by device class.

### Lawnchair-specific features

* **Preferences screen**
  * User-facing settings UI used to configure launcher behavior.
* **Default launcher**
  * The launcher app currently selected by Android to handle Home intent.
* `PreferenceManager2`
  * Lawnchair's modern settings layer used for most feature preferences.
* `ReloadHelper`
  * Utility that triggers launcher reloads after preference or profile changes.
* **Icon Pack**
  * Third-party icon provider used to replace default app icons.
* **Icon Shape**
  * User-selectable icon mask style such as `circle` or `squircle`.
* **Themed Icons**
  * Icons tinted to match system or wallpaper-derived dynamic colors.
* **Color tokens**
  * Theme abstraction values used to keep colors consistent across UI states.
* **Hidden apps**
  * User-selected apps excluded from normal app drawer visibility.
* **Feed integration**
  * Optional left-page content integration such as a Discover-style feed.
* **Overlay mode**
  * Visual transition style used when opening or closing apps.

### Search

* **QSB (Quick Search Bar)**
  * Search entry surface shown in Workspace, Hotseat, and All Apps contexts.
* **Search Provider**
  * Source implementation that returns search results such as apps or web suggestions.
* **Local search**
  * On-device search mode that prioritizes launcher data and indexed content.
* **Web search**
  * Online search mode delegated to a web-capable provider.

### Smartspace

* **Smartspace**
  * The At a Glance style surface for contextual information like weather and events.
* **Smartspace provider**
  * Data source implementation that supplies Smartspace cards.
* **Predictions**
  * Suggested apps or targets ranked by usage context.

### Launcher gestures

* **Gesture handler**
  * Component that maps gesture input to launcher actions.
* **DT2S (Double Tap to Sleep)**
  * Gesture action that turns the screen off from launcher surfaces.
* **Long-press**
  * Press-and-hold interaction used to open menus or start drag operations.
* **Swipe-up**
  * Primary gesture used to open All Apps or enter task navigation flows.

### Quickstep and Recents

* **Gesture navigation**
  * Navigation mode that uses edge and swipe gestures instead of buttons.
* **Recents**
  * The task-switching surface that shows recent running tasks.
* **Overview**
  * Alternate name for the Recents task-switching surface.
* `RecentsView`
  * Core view responsible for rendering and managing task cards in Recents.
* `TaskView`
  * UI card representing a single task inside RecentsView.
* `GestureState`
  * State machine tracking the current swipe and transition lifecycle.
* `GestureEndTarget`
  * The resolved destination of a gesture, such as HOME or RECENTS.
* `AbsSwipeUpHandler`
  * Core handler that drives swipe-up transition behavior.
* `RecentsAnimation`
  * Animation pipeline that synchronizes app surfaces during task transitions.
* `RemoteAnimationTarget`
  * System object representing an app surface under remote animation.
* **Taskbar**
  * Persistent app bar surface used in supported modes and form factors.
* **Taskbar stash and unstash**
  * Taskbar collapse and restore behavior tied to app and launcher state.
