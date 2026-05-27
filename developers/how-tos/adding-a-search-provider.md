# Adding a search provider

The dock search bar (hotseat qsb) supports multiple search providers.

New web-based search engines can be added by implementing the search provider contract and registering them in the centralized provider list.

### Implementation contract

Search providers are defined as Kotlin objects that inherit from the `QsbSearchProvider` sealed class. Each provider requires the following metadata:

* A unique string ID used for preference storage.
* A reference to a string resource for the display name.
* A reference to a vector drawable for the icon.
* A package name (leave empty for website-only providers).
* A search URL for the website fallback.
* A provider type, typically set to `QsbProviderType.WEBSITE`.

### Steps to add a provider

{% stepper %}
{% step %}
Create a new class in `lawnchair/app/lawnchair/qsb/providers/`. Name it `SearchEngineName`.
{% endstep %}

{% step %}
Use the following template to define your engine. Replace the placeholders with your specific engine details.

```kotlin
data object MyEngine : QsbSearchProvider(
    id = "my_engine",
    name = R.string.search_provider_my_engine,
    icon = R.drawable.ic_my_engine,
    packageName = "",
    website = "https://my-engine-url.com/search?q=",
    type = QsbProviderType.WEBSITE,
)
```
{% endstep %}

{% step %}
Add the required vector drawable to the `lawnchair/res/drawable/` directory and the engine name string to `lawnchair/res/values/strings.xml`.
{% endstep %}

{% step %}
Register the provider in `QsbSearchProvider` and locate the `companion object`. Add your new engine to the list returned by the `values()` function. Maintain alphabetical order to keep the list organized.

```kotlin
sealed class QsbSearchProvider(...) {
    // ...
    companion object {
        fun values() = listOf(
            AppSearch,
            Bing,
            DuckDuckGo,
            Google,
            MyEngine, // Added provider
        )
    }
}
```
{% endstep %}
{% endstepper %}

Once registered, the new provider will appear in the search provider selection menu within Lawnchair settings.
