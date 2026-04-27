---
description: Set up dock and app drawer search, providers, and result types.
icon: magnifying-glass
---

# Search

Lawnchair search helps you find apps, contacts, settings, files, and web results.

Use **Home settings** → **Search bar** to configure it.

### Dock search bar

The dock search bar sits at the bottom of the home screen.

Go to **Home settings** → **Search bar** → **Dock** to change it.

<details>

<summary>Hide the search bar</summary>

1. Tap **Search bar widget**.
2. Select **Disabled**.

</details>

<details>

<summary>Change the search provider</summary>

A **search provider** is the service or app that opens when you tap the search bar.

1. Tap **Search provider**.
2. Choose your preferred provider from the list.
   * Some providers may require an app to be installed. Tap **Download** <i class="fa-arrow-down-to-line">:arrow-down-to-line:</i> to install it.
   * When choosing **Website**, Lawnchair will open the provider's search website in your default web browser.

</details>

<details>

<summary>Customize its appearance</summary>

You can adjust the search bar under the **Style** section.

* **Apply accent color**: Matches the search bar to the current theme.
* **Outline width**: Changes the border width. You can also set the border color when the value is not `0`.

</details>

### App drawer search bar

The app drawer search bar is built for searching both on-device content and the web.

Go to **Home settings** → **Search bar** → **App drawer** to change it.

<details open>

<summary>What does <strong>Match dock search bar actions</strong> do?</summary>

This option links the behavior and appearance of both search bars:

* When turned on, the search bar will inherit the theme and icons of the dock search bar.
* Tapping the dock search bar will open the app drawer search UI instead of launching the selected search provider.

</details>

<details>

<summary>Choose the search algorithm</summary>

You can choose which backend Lawnchair uses to find results in the app drawer.

1. Tap **Search algorithm**.
2. Choose an algorithm from the list.
   1. **App search**: Searches installed apps only.
   2. **Global search (on-device)**: Searches apps, contacts, files, settings, and other local sources.

</details>

<details>

<summary>Choose local result types</summary>

If you choose **Global search (on-device)**, more options appear under **Show in search results**.

You can turn categories on or off. Some categories also have their own settings.

* **Apps and shortcuts**
  * Supports fuzzy matching, so small typos still work.
* **Web suggestions**
  * Lets you choose a built-in provider or a custom one.
  * If you use a custom provider, follow the URL instructions shown in settings.
* **People**
  * Searches contacts and related information.
* **Files**
  * Searches your device storage.
  * You can limit results to photos and videos, audio files, or all files.
  * In the Play Store version, **All files** access is not available because of Play Store restrictions.
* **Android settings**
  * Searches system settings.
* **Search history**
  * Shows recent queries when you tap the search bar.
* **Calculator**
  * Runs calculations directly in the search bar.

</details>

### Common issues

<details>

<summary>Search results are incomplete or not appearing</summary>

* Check your selected **Search algorithm**. Ensure it matches the type of results you expect.
* If you use **Global search (on-device)**, make sure the right result types are turned on.
* Ensure Lawnchair has the permissions it needs.
* Check [Battery optimization](../troubleshooting/battery-optimization.md).

</details>

<details>

<summary>Web search or web suggestions are not working</summary>

* Check if you have a stable internet connection.
* Check if **Web suggestions** is turned on.
* Verify your selected **Web suggestions** provider.
  * If you use a custom provider, check that the URL is valid.

</details>

<details>

<summary>Tapping the home screen search bar opens the app drawer search instead of my selected provider</summary>

See [What does **Match dock search bar actions** do?](search.md#what-does-match-dock-search-bar-actions-do).

</details>
