# Theming and icons

Lawnchair offers options to customize the look and feel of your home screen, including icons, colors, and fonts. This guide explains how to customize these visual elements.

### Customizing icons

Lawnchair handles icon customization through two primary systems that can interact with each other.

#### Icon packs

Icon packs provide a set of custom, full-color designs for your app icons.

<details open>

<summary>How to apply icon packs</summary>

1. Navigate to **Home settings** > **General**.
2. Tap **Icon style**.
3. Select your desired icon pack from the list.

</details>

<details open>

<summary>What does <strong>Tint with accent color</strong> do?</summary>

When turned on, it applies your current accent color (determined by your theme or wallpaper) to all icons, regardless of whether the icon pack is designed for it.

This can create a uniform look but may override an icon pack's intended colors in a way that appears invasive or less refined for some apps.

</details>

<details>

<summary>Where to find icon packs</summary>

You can find supported icon packs through different online sources:

* [Play Store](https://play.google.com/store/search?q=icon+pack\&c=apps)
* [F-Droid](https://f-droid.org/en/categories/icon-pack/)

</details>

#### Themed icons

Themed icons are a modern Android feature that provides single-color, monochrome versions of icons. Lawnchair then dynamically colors these icons to match your device's wallpaper and theme.

{% include "../.gitbook/includes/turn-on-themed-icons.md" %}

{% hint style="info" %}
For the best themed icon experience, ensure you have a compatible icon source.

Lawnicons is specifically designed to provide high-quality themed icons for Lawnchair and can be set as both your "Icon pack" and your "themed icon source." Refer to the [Lawnicons integration page](../integrations/lawnicons.md) for full details.
{% endhint %}

#### Per-icon customization

You can manually change the icon for a specific app on your home screen or in the app drawer.

{% hint style="warning" %}
**Important:** This feature is only supported for app icons, and does not support shortcuts or apps in your work profile.
{% endhint %}

To customize an individual icon:

1. Long-press the app icon you wish to change.
2. Tap **Customize** (or the pencil icon).
3. Tap the existing icon to open the icon editor.
   * From here, you can choose an icon from your installed icon packs.

### Customizing colors and theme

Lawnchair allows you to adjust its color scheme to match your preferences or your device's theme.

<details>

<summary>Adjusting accent color source</summary>

This settings determines how Lawnchair picks its primary colors for various UI elements.

1. Navigate to **Home settings** > **General**.
2. Tap **Accent color**.
3. Choose between the following:
   1. **System**: Uses the colors provided by your device.
   2. **Wallpaper**: Uses the colors sampled from your wallpaper.
      * If you are using a live wallpaper, Lawnchair may not sample colors reliably.
   3. **Custom**: You can choose between the pre-sets, or set a custom color.

</details>

<details>

<summary>Adjusting color style</summary>

If you are using a non-system accent color, you can also change how Lawnchair applies the colors.

1. Navigate to **Home settings** > **General**.
2. Check if your current **Accent color** is not **System**.
3. Tap **Color style**.
4. Choose an item from the list to see how it will look.

</details>

### Common issues

<details>

<summary>Custom font not applying or reverts</summary>

Sometimes, after changing fonts, a restart of Lawnchair is needed for the changes to take full effect.

* Navigate to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
* Tap **Restart Lawnchair**.

</details>

<details>

<summary>Icons appear strangely tinted or have unexpected colors</summary>

Try to turn off **Tint with accent color** via the steps in [#what-does-tint-with-accent-color-do](theming-and-icons.md#what-does-tint-with-accent-color-do "mention").

</details>
