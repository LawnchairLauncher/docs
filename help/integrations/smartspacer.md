---
description: Replace At a Glance or add a custom feed with Smartspacer.
icon: bars-sort
---

# Smartspacer

[Smartspacer](https://github.com/KieronQuinn/Smartspacer) is an app that replaces Google's At a Glance feature and adds extra customization and plugin support.

Lawnchair supports Smartspacer as both an At a Glance provider and a feed provider.

### Prerequisites

* A device running Android 10 or later
* The Smartspacer app installed

### Use Smartspacer in Lawnchair

You can use Smartspacer for either feature, or both.

#### As an At a Glance replacement

1. Go to **Home settings** → **At a Glance**.
2. Tap **At a Glance provider**, then select **Smartspacer** from the list.
3. Return to your home screen. You will see a message that says **Smartspacer Permission Required**. Tap it.
4. In the permission dialog that appears, tap **Allow**.

#### As an alternative feed provider

1. Go to **Home settings** → **Home screen**.
2. Turn on the **Show feed** option.
3. Tap **Feed provider**, then select **Smartspacer** from the list.

### Adjust settings

Most Smartspacer features, such as plugins and appearance, are managed in the Smartspacer app itself.

You can open Smartspacer settings in one of three ways:

* Long-press At a Glance, then tap **Customize**.
* Go to **Home settings** → **At a Glance**, then tap **Open Smartspacer settings**.
* Open the **Smartspacer** app.

Lawnchair provides one specific setting for the widget:

1. Go to **Home settings** → **At a Glance**.
2. Under **Smartspacer settings**, adjust the slider for **Maximum number of targets**.

### Common issues

Some issues come from Smartspacer itself. Before reporting a Lawnchair bug, check [Smartspacer issues](https://github.com/KieronQuinn/Smartspacer/issues).

<details>

<summary>Smartspacer disappeared from my home screen</summary>

If the widget disappears, restarting Lawnchair often restores it:

{% include "../.gitbook/includes/restart-lawnchair.md" %}

</details>

<details>

<summary>The widget is misaligned or has incorrect padding</summary>

This is a known Lawnchair issue. Alignment can be inconsistent on some screen densities and grid layouts.

There is currently no manual fix for this in Lawnchair settings.

</details>
