# Smartspacer

[Smartspacer](https://github.com/KieronQuinn/Smartspacer) is an app that provides a drop-in replacement to Google Pixel's At a Glance feature, while also supporting extended customization and custom plugins.

Lawnchair supports Smartspacer by providing support with replacing Lawnchair's At a Glance and default feed.

### Prerequisites

* A device with Android 10 and above
* The Smartspacer app installed

### How to use Smartspacer

You can set up Smartspacer for either or both of its functions.

#### As an At a Glance replacement

1. Navigate to **Home settings** > **At a Glance**.
2. Tap **At a Glance provider**, then select **Smartspacer** from the list.
3. Return to your home screen. You will see a message that says **Smartspacer Permission Required**. Tap it.
4. In the permission dialog that appears, tap **Allow**.

#### As an alternative feed provider

1. Navigate to **Home settings** > **Home screen**.
2. Turn on the **Show feed** option.
3. Tap **Feed provider**, then select **Smartspacer** from the list.

### Adjust settings

Most of Smartspacer's features, like plugins and appearance, can be change within the Smartspacer app itself, not within Lawnchair.

You can open Smartspacer settings in one of three ways:

* Long-press at At a Glance, then tap **Customize**.
* Navigate to **Home settings > At a Glance**, then tap **Open Smartspacer settings**
* Open the **Smartspacer** app.

Lawnchair provides one specific setting for the widget:

1. Navigate to **Home settings > At a Glance.**
2. Under **Smartspacer settings**, adjust the slider for **Maximum number of targets**.

### Common issues

Some issues may originate from the Smartspacer app itself. Before reporting a bug to Lawnchair, visit [Smartspacer's GitHub repository](https://github.com/KieronQuinn/Smartspacer/issues) to see if it's an issue caused by the app.

<details>

<summary>Smartspacer disappeared from my home screen</summary>

If the widget disappears, you can often restore it by restarting Lawnchair:

1. Open **Home settings**.
2. Tap the three-dots at the top right.
3. Tap **Restart Lawnchair**.

</details>

<details>

<summary>The widget is misaligned or has incorrect padding</summary>

This is a known issue within Lawnchair. The widget's alignment can be inconsistent, particularly on certain screen densities or when using specific grid layouts. This occurs because Lawnchair's calculation for widget padding and its interaction with the home screen grid sometimes leads to misalignment.

The Lawnchair team is aware of this behavior and is working to address it. Currently, there is no manual adjustment for this within Lawnchair's settings.

</details>
