---
description: Change icon packs, themed icons, colors, and fonts.
icon: palette
---

# Theming and icons

Lawnchair lets you customize icons, colors, and fonts. Use these settings to match your home screen to your style.

### Customize icons

Lawnchair supports two icon systems that can work together.

#### Icon packs

Icon packs provide a set of custom, full-color designs for your app icons.

<details open>

<summary>How to apply icon packs</summary>

1. Go to **Home settings** > **General**.
2. Tap **Icon style**.
3. Select the icon pack you want.

</details>

<details open>

<summary>What does <strong>Tint with accent color</strong> do?</summary>

When turned on, Lawnchair applies your current accent color to all icons.

This creates a more uniform look, but it can override an icon pack's intended colors.

</details>

<details>

<summary>Where to find icon packs</summary>

You can find supported icon packs here:

* [Play Store](https://play.google.com/store/search?q=icon+pack\&c=apps)
* [F-Droid](https://f-droid.org/en/categories/icon-pack/)

</details>

#### Themed icons

Themed icons are a modern Android feature that provides single-color, monochrome versions of icons. Lawnchair recolors them to match your wallpaper and theme.

{% include "../.gitbook/includes/turn-on-themed-icons.md" %}

{% hint style="info" %}
For the best themed icon experience, make sure you have a compatible icon source.

Lawnicons is built for Lawnchair and works as both an icon pack and a themed icon source. See [Lawnicons](../integrations/lawnicons.md) for details.
{% endhint %}

#### Per-icon customization

You can also change the icon for a specific app on the home screen or in the app drawer.

{% hint style="warning" %}
**Important:** This feature only works for app icons. It does not support shortcuts or work profile apps.
{% endhint %}

To change one icon:

1. Long-press the app icon you want to change.
2. Tap **Customize** (or the pencil icon).
3. Tap the existing icon to open the icon editor.
   * Choose an icon from your installed icon packs.

### Customize colors and theme

Lawnchair also lets you adjust its color scheme.

<details>

<summary>Adjusting accent color source</summary>

This setting controls how Lawnchair picks its main colors.

1. Go to **Home settings** > **General**.
2. Tap **Accent color**.
3. Choose one of these options:
   1. **System**: Uses the colors provided by your device.
   2. **Wallpaper**: Uses the colors sampled from your wallpaper.
      * If you are using a live wallpaper, Lawnchair may not sample colors reliably.
   3. **Custom**: Lets you choose a preset or set a custom color.

</details>

<details>

<summary>Adjusting color style</summary>

If you use a non-system accent color, you can also change how Lawnchair applies it.

1. Go to **Home settings** > **General**.
2. Make sure **Accent color** is not set to **System**.
3. Tap **Color style**.
4. Choose a style from the list.

</details>

### Common issues

<details>

<summary>Custom font not applying or reverts</summary>

After changing fonts, you may need to restart Lawnchair.

* Go to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
* Tap **Restart Lawnchair**.

</details>

<details>

<summary>Icons appear strangely tinted or have unexpected colors</summary>

Turn off **Tint with accent color** by following the steps in [What does **Tint with accent color** do?](theming-and-icons.md#what-does-tint-with-accent-color-do).

</details>
