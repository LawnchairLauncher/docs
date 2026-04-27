# Search

Lawnchair offers powerful and customizable search capabilities, allowing you to find apps, contacts, settings, and perform web searches directly from your home screen or app drawer.

This guide will help you understand and personalize Lawnchair's search experience.

### Dock search bar

The search bar located in the dock (bottom row of the home screen) serves as a quick entry point for various search actions.

To change its settings, navigate to **Home settings** > **Search bar**, then tap **Dock**.

<details>

<summary>Hiding the search bar</summary>

1. Tap **Search bar widget**.
2. On the list that appears, tap **Disabled**.

</details>

<details>

<summary>Changing the search provider</summary>

A **search provider** is the service or app that opens when you tap the search bar.

1. Tap **Search provider**
2. Choose your preferred provider from the list.
   * Some providers may require an app to be installed. Tap **Download** <i class="fa-arrow-down-to-line">:arrow-down-to-line:</i> to install it.
   * When choosing **Website**, Lawnchair will open the provider's search website in your default web browser.

</details>

<details>

<summary>Customizing its appearance</summary>

You can adjusy the search bar appearance by changing the settings under the **Style** section.

* **Apply accent color**: When on, the search bar's background and icons will match the system theme.
* **Outline width**: This setting adjusts the border shown in the search bar. You can also adjust the color when the value is not 0.

</details>

### App drawer search bar

The search bar in the app drawer is optimized for finding content on both your device and the web.

To change its settings, navigate to **Home settings** > **Search bar**, then tap **App drawer**.

<details open>

<summary>What does <strong>Match dock search bar actions</strong> do?</summary>

This option links the behavior and appearance of the two search bars:

* When turned on, the search bar will inherit the theme and icons of the dock search bar.
* Additionally, tapping the dock search bar will directly open the app drawer's search UI, rather than launching the selected search provider app or website.

</details>

<details>

<summary>Customizing the search algorithm</summary>

You can choose which backend Lawnchair uses to find results in the app drawer.

1. Tap **Search algorithm**.
2. Choose an algorithm from the list.
   1. **App search**: Searches only installed applications on your device
   2. **Global search (on-device):** Searches multiple local sources on your device, including apps, contacts, files, and settings

</details>

<details>

<summary>Customizing local search result types</summary>

If you choose the **Global search (on-device)** algorithm, several items will appear in the **Show in search results section**.

You can turn on or off individual categories, and if there is a vertical line, optionally adjust settings within that result type.

* **Apps and shortcuts**
  * Includes support for fuzzy searching (finds apps even with typos)
* **Web suggestions**
  * Allows choosing a provider from the built in list or a custom one.
  * If using a custom provider, follow the instructions shown when changing the URL settings.
* **People**
  * Searches your contacts and other related information
* **Files**
  * Searches your device's media storage.
  * You can refine this to only show photos and videos, audio files, or all.
  * **Important**: In the Play Store version, you cannot grant access to **All files**. This is due to Play Store restrictions.
* **Android settings**
  * Searches for system settings.
* **Search history**
  * Displays your recent queries when you first tap the search bar.
* **Calculator**
  * Performs real-time math calculations directly in the search bar.

</details>

### Common issues

<details>

<summary>Search results are incomplete or not appearing</summary>

* Check your selected **Search algorithm**. Ensure it matches the type of results you expect.
* If using **Global Search (on-device)**, check if the desired **Result types** are turned on.
* Ensure Lawnchair has necessary permissions to do the search.
* [Check your device's battery optimization settings](../troubleshooting/battery-optimization.md).

</details>

<details>

<summary>Web search or web suggestions are not working</summary>

* Check if you have a stable internet connection.
* Check if **Web suggestions** is turned on
* Verify your selected **Web suggestions** provider.
  * If you are using a custom web suggestion provider, check if the URL syntax is correct.

</details>

<details>

<summary>Tapping the Home Screen search bar opens the App Drawer search instead of my selected provider:</summary>

See [#what-does-match-dock-search-bar-actions-do](search.md#what-does-match-dock-search-bar-actions-do "mention")

</details>
