# Getting started

This page lists details on how to get started with developing Lawnchair.

This page assumes familiarity with Kotlin, Jetpack Compose, and the basics of Android development. We also assume that you've read [the Lawnchair contributing guide](https://github.com/LawnchairLauncher/lawnchair/blob/16-dev/CONTRIBUTING.md).

{% hint style="info" %}
Lawnchair is a complex project, containing code both from AOSP and several compatibility layers. It is normal to be confused at first - make sure to take the code step-by-step, making smaller contributions first. Don't try to change all of Launcher3 views to Jetpack Compose as your first contribution!
{% endhint %}

### Common launcher terms

* Launcher - an Android app serving as the "home screen" for a given device
* Launcher3 - the default AOSP implementation of the launcher
* Workspace - represents the homescreen
* Hotseat - represents the dock
* Allapps - represents the app drawer
* Smartspace - represents At a Glance. The smartspace view actually is one of the QSB views (it acts as the first item spanning the whole grid)
* Quickstep - represents the Recents view and integration
* QSB - quick _search bar_. There are three of them: one in the workspace, one in the hotseat, and one in the allapps view.
* DT2S - double tap to sleep
* Device Profile - important aspects of the device, like size and orientation
* IDP - invariant device profile - refers to the the device profile that does not need activity access. This forms the basis of the launcher grid and UI

#### Other terminology

* `MINUS_ONE_PAGE`: refers to the home screen page used by feed integrations, such as Google Feed. One can add a new feed by [creating a service in a different app](https://github.com/FabianTerhorst/DrawerOverlayService) then adding it to Lawnchair's whitelist.

### Architectural overview

Lawnchair contains several distinct packages, as stated in the contributing guidelines. Each module is described in more detail below:

* `lawnchair` package - contains all the relevant code relating to Lawnchair customizations, including `PreferenceActivity`
* `src` package - contains most of the code used to power Launcher3
* `quickstep` package - connects Launcher3 to the Recents screen, and other system-only behaviors.
* [`platforms/frameworks/libs/systemui`](https://github.com/LawnchairLauncher/platform_frameworks_libs_systemui) - contains multiple libraries in SystemUI used by Lawnchair. See the linked repository for further information.

### Simple tasks

#### Adding a new hotseat QSB provider

{% stepper %}
{% step %}
Create a new class in `lawnchair/app/lawnchair/qsb/providers/`. Name it `SearchEngineName`.
{% endstep %}

{% step %}
Make the class inherit from QsbSearchProvider. Visit the other providers for additional examples. For a website, a general template is as follows:

```kotlin
data object Engine : QsbSearchProvider(
    id = "engine",
    name = R.string.search_provider_engine,
    icon = R.drawable.ic_engine,
    packageName = "",
    website = "https://engine-url.com/",
    type = QsbProviderType.WEBSITE,
)
```
{% endstep %}

{% step %}
Add the vector drawables and the missing strings in the `lawnchair/res/` folder.
{% endstep %}

{% step %}
Add the engine name in `QsbSearchProvider`, sorted alphabetically:

```kotlin
sealed class QsbSearchProvider(...) {
     // ...
    companion object {
        // ...
        fun values() = listOf(
            AppSearch,
            EngineName,
            // other engines go here
       )
// ...
```
{% endstep %}

{% step %}
Done! You're ready to open a PR.
{% endstep %}
{% endstepper %}

### Parts of Lawnchair's UI

Lawnchair uses the view system and Jetpack Compose (Compose) for most of its UI.

Views are used within:

* All of the non-modified parts of Launcher3's UI
* Search (both in the QSB and the search result UI)
* Smartspace

Compose is used within:

* Lawnchair settings
* Custom bottom sheet pop-ups

### Preferences system

#### About handling Lawnchair's preferences

Lawnchair's preferences are handled via the following:

* [`PreferenceManager` (`prefs`)](https://github.com/LawnchairLauncher/lawnchair/blob/14-dev/lawnchair/src/app/lawnchair/preferences/PreferenceManager.kt), using SharedPreferences as the backend
* [`PreferenceManager2` (`prefs2`)](https://github.com/LawnchairLauncher/lawnchair/blob/14-dev/lawnchair/src/app/lawnchair/preferences2/PreferenceManager2.kt), using Preference Datastore as the backend

Prefer adding new settings in `prefs2` over `prefs`, as the former provides the ability to use non-primitive data types and getting the default value from `config.xml`.

#### Implementing a new preference

First, make a new key. We will use `example_pref` as the key, with a `Boolean` type defaulting to `false`. Depending on whether you use `prefs` or `prefs2`, the code may differ slightly. See the below code block for more info.

```kotlin
// PreferenceManager.kt
class PreferenceManager : ... {
    // ...
    val examplePref = BoolPref("example_pref", false)
}

// PreferenceManager2.kt
class PreferenceManger2 ... {
    // ...
    val examplePref = preference(
        key = booleanPreferencesKey(name = "example_pref"),
        defaultValue = false,
    )
}
```

#### Using the new preference

The preference can be used by getting either the `prefs` or `prefs2` instance:

```kotlin
val prefs = PreferenceManager.getInstance(context)
val prefs2 = PreferenceManager2.getInstance(context)
```

To actually use the preference, you need to get the preference key value first:

```kotlin
// For prefs
val key: Boolean = prefs.examplePref.get()

// For prefs2
val key: Boolean  = prefs2.examplePref.firstBlocking()
```

Setting the preference value shouldn't really happen within a launcher UI, but rather in the Preferences UI. See the next section to view info about that.

#### Using the `adapter` system

The `.getAdapter()` system, used both by `prefs` and `prefs2`, allows for uniform state handling of preferences in the Lawnchair settings UI.

See the below code block for explanations.

```kotlin
@Composable
fun BasicExample() {
    val prefs = preferenceManager()
    val prefs2 = preferenceManager2()

    val key = prefs.examplePref.getAdapter()
    // or, for prefs2:
    val key = prefs2.examplePref.getAdapter()
    
    // SwitchPreference allows you to handle Boolean preferences
    SwitchPreference(
        adapter = key,
        label = "Example pref",
    )
}

@Composable
fun BasicExampleWithCustomComponent() {
    val prefs2 = preferenceManager2()
    val key = prefs2.examplePref.getAdapter()

    val value = key.state.value // get the boolean value as Compose state
    Column {
        Text("State: $value")
        Button(
            onClick = {
                // changes the value to a new value (for here, the inverse of the boolean) and updates the compose state
                key.onChange(value = !it)
            }
        ) {
            Text("Toggle state")
        }
    }
}
```
