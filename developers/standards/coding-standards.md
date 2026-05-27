# Coding standards

Lawnchair code must be logical, well-formatted, and respect the architectural zone it inhabits.

### Language conventions

As seen in the [project overview](../architecture/project-overview.md), Lawnchair uses a mix of paradigms:

* For Kotlin, follow the official [Kotlin coding conventions](https://kotlinlang.org/docs/coding-conventions.html).
  * New Lawnchair-specific features must be written in Kotlin.
* For existing Java code, follow the existing style seen in the codebase.&#x20;
* Place Lawnchair-specific logic in the `lawnchair` package. Minimize changes to the `src` package to facilitate AOSP rebases.

### Modifying AOSP files

When modifying AOSP files, document changes you made with the prefix `LC-Note(<optional modifier>): <reason>` and logs with the prefix `LC-`:

```java
// Example
// LC-Note: These changes are needed to support API X.
public void onChange(Boolean value) {
    Log.d("LC-BaseActivity", "Doing something on change")
    ...
}
```

### String naming

Strings in `strings.xml` must follow the standardized naming format to ensure maintainability and ease of translation.

<table><thead><tr><th width="202">Type</th><th width="177">Format</th><th width="240">Example</th></tr></thead><tbody><tr><td>Generic word</td><td><code>$1</code></td><td><code>disagree</code></td></tr><tr><td>Action</td><td><code>$1_action</code></td><td><code>apply_action</code></td></tr><tr><td>Preference label</td><td><code>$1_label</code></td><td><code>folders_label</code></td></tr><tr><td>Preference description</td><td><code>$1_description</code></td><td><code>folders_description</code></td></tr><tr><td>Preference choice</td><td><code>$1_choice</code></td><td><code>off_choice</code></td></tr><tr><td>Feature string</td><td><code>[feature]_$1</code></td><td><code>colorpicker_hsb</code></td></tr><tr><td>Launcher string</td><td><code>$1_launcher</code></td><td><code>device_contacts_launcher</code></td></tr></tbody></table>

Avoid using generic names for feature-specific strings to prevent conflicts during rebases.
