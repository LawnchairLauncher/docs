# Preferences

Lawnchair's customization is driven by a centralized preference system. This system acts as the single source of truth for the project's state, bridging the modern UI layer with the legacy AOSP core.

State management in Lawnchair relies on reading these preferences throughout the launcher and modifying them almost exclusively within the settings UI.

### Preference managers

Lawnchair utilizes two distinct preference managers:

* [`PreferenceManager` (`prefs`)](https://github.com/LawnchairLauncher/lawnchair/blob/16-dev/lawnchair/src/app/lawnchair/preferences/PreferenceManager.kt): The legacy manager utilizing `SharedPreferences` as the backend. Avoid adding new keys to this manager.
* [`PreferenceManager2` (`prefs2`)](https://github.com/LawnchairLauncher/lawnchair/blob/16-dev/lawnchair/src/app/lawnchair/preferences2/PreferenceManager2.kt): The modern manager utilizing Preference Datastore. This is the required location for all new settings, as it supports non-primitive data types and allows fetching default values from `config.xml`.

### Implementing a new preference

When adding a new setting, you must define it within `PreferenceManager2`.

The following example defines a `Boolean` preference named `example_pref` that defaults to `false`.

```kotlin
// PreferenceManager2.kt
class PreferenceManger2 ... {
    // ...
    val examplePref = preference(
        key = booleanPreferencesKey(name = "example_pref"),
        defaultValue = false,
    )
}
```

_Note: For legacy compatibility, a preference in `PreferenceManager` would be defined as `val examplePref = BoolPref("example_pref", false)`._

### Reading preference values

Preferences are primarily read by the core launcher logic to determine system behavior. To use a preference, you must first acquire the manager instance and then fetch the value of the specific key.

```kotlin
val prefs2 = PreferenceManager2.getInstance(context)

// Retrieve the current boolean value
val key: Boolean = prefs2.examplePref.firstBlocking()
```

_Note: For legacy `prefs`, the retrieval method is `prefs.examplePref.get()`._

Setting preference values should generally not occur within the core launcher UI or Quickstep logic. Modifying state is the responsibility of the Lawnchair settings UI.

### Using the adapter system in Compose

As seen in [Lawnchair design patterns](../architecture/lawnchair-design-patterns.md), the app employs a Pragmatic MAD approach for its settings UI. Rather than creating ViewModels for simple settings screens, we use the `.getAdapter()` system.

The adapter provides uniform, reactive state handling directly within Jetpack Compose components.&#x20;

#### **Standard preference components**

For standard settings (like toggles or sliders), pass the adapter directly to the provided Lawnchair UI components.

```kotlin
@Composable
fun BasicExample() {
    val prefs2 = preferenceManager2()
    
    // SwitchPreference automatically handles reading and writing the boolean state
    SwitchPreference(
        adapter = prefs2.examplePref.getAdapter(),
        label = stringResource(R.string.example_pref_label),
    )
}
```

#### **Custom Compose components**

When building complex or custom UI elements that require preference access, you can read the reactive state and trigger updates manually through the adapter.

```kotlin
@Composable
fun BasicExampleWithCustomComponent() {
    val prefs2 = preferenceManager2()
    val adapter = prefs2.examplePref.getAdapter()

    // Retrieve the boolean value as a reactive Compose state
    val value = adapter.state.value 

    Column {
        Text("Current state: $value")
        Button(
            onClick = {
                // Write the new value to persistent storage and update the Compose state
                adapter.onChange(value = !value)
            }
        ) {
            Text("Toggle state")
        }
    }
}
```
