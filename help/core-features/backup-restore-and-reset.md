---
description: Back up your setup, restore it later, or reset Lawnchair.
icon: arrows-rotate
---

# Backup, restore, and reset

Lawnchair can back up your settings, home screen layout, and app drawer setup.

You can also restore that backup later or reset Lawnchair to its default state.

### Creating a backup

<details open>

<summary>What gets backed up</summary>

Most settings are backed up automatically, including:

* Your home screen layout, including icon positions and folders
* App drawer and search settings
* Most Lawnchair settings, including gestures and theme settings

</details>

<details open>

<summary>What is not included in a backup</summary>

* **Widgets**
  * Widget placement is saved, but widget data and internal configuration are not.
  * You need to reconfigure widgets after a restore.
* **Third-party apps**
  * Integrations such as icon packs and Smartspacer still require their related apps to be installed.
  * If those apps are missing, Lawnchair falls back to its default settings.
* **Work profile apps**
  * Work profile apps may not restore reliably because Android handles them inconsistently.
* **Apps not installed**
  * If an app is missing on the target device, its icon will not appear after restore.

</details>

To create a backup:

1. Go to **Home settings** → **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-cloud-plus">:cloud-plus:</i> **Create backup**.
3. Choose what to include:
   * **Layout and settings**: Backs up everything noted above.
   * **Wallpaper**: Backs up your current wallpaper. This setting does not work if you have a live wallpaper.
4. Tap **Create**. You will be prompted to choose a name and location for your backup file.
   * Save it somewhere easy to access, such as **Downloads** or a cloud drive folder.
   * The file will have a `.lawnchairbackup` extension (e.g., `Lawnchair_Backup January 01, 2026 00:00:00.lawnchairbackup`).

### Restoring a backup

Restoring applies a previously saved `.lawnchairbackup` file to your current Lawnchair installation.

To restore a backup:

1. Go to **Home settings** → **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-arrow-rotate-left">:arrow-rotate-left:</i> **Restore backup**.
3. On the screen that appears, find and select your backup file.
4. After selecting a backup, you can restore **Layout and settings**, **Wallpaper**, or both.
   * See **What gets backed up** for details.
5. Tap **Restore**.

### Restoring a Nova backup

On Lawnchair 15 Beta 3 and later, you can import some home screen settings from a Nova Launcher backup file (`.novabackup`).

This helps if you are moving from Nova Launcher.

<details>

<summary>What gets restored from a Nova backup</summary>

* Home screen grid layout
* Icons and their positions
* Widget placement, but not widget data or setup
* Folders and their contents, if the apps are installed
* The selected icon pack, if it is installed

</details>

<details>

<summary>What is <em>not</em> restored from a backup</summary>

* Nova-specific settings such as Nova gestures and notification badges
* Subgrid layouts. Lawnchair aligns these items to the nearest standard grid position.
* App drawer layout, categories, and settings
* Lawnchair-specific settings
* Apps that are not installed on your device

</details>

To restore a Nova backup:

1. Go to **Home settings** → **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-arrow-rotate-left">:arrow-rotate-left:</i> **Restore Nova backup**.
3. On the screen that appears, find and select your backup file.
4. A confirmation screen will appear, showing a summary of what will be restored.
   * If your Nova setup used subgrid positioning, Lawnchair will warn you that those items will be aligned to the standard grid.
   * You can optionally tap **Add extra row to show At a Glance** if you wish to show this feature.
5. Tap **Restore**.

### Reset settings to default

This resets Lawnchair to its default state.

All custom settings, including your home screen layout, will be lost.

{% hint style="danger" %}
**Important:** This action is irreversible. Ensure you have created a backup if you wish to save your current setup before proceeding.
{% endhint %}

To reset Lawnchair:

1. Go to **Home settings** → **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-circle-info">:circle-info:</i> **App info**.
3. On the screen that appears, tap **Storage and cache**.
4. Tap <i class="fa-trash-can">:trash-can:</i> **Clear storage**.
5. On the warning that appears, tap **Delete**.

### Troubleshooting

<details>

<summary>Can't find backup file</summary>

Make sure the `.lawnchairbackup` file is stored on internal storage or in a cloud location your file picker can access.

</details>

<details>

<summary>Can't restore the backup file</summary>

If your backup fails to restore:

* Ensure the filename does not contain unusual or unsupported characters. Try renaming it to something simple, such as `backup.lawnchairbackup`.
* Make sure the file is fully downloaded to your device.
* Ensure the backup is compatible with your installed Lawnchair version.
* Re-download or recreate the backup if you suspect it is corrupted.

</details>
