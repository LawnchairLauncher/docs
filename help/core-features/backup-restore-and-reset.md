# Backup, restore, and reset

Lawnchair allows you to back up your customized settings, home screen layout, and app drawer configuration. This is useful for transferring your setup to a new device, saving a specific configuration, or restoring after a factory reset. You can also reset Lawnchair to its default state.

### Creating a backup

<details open>

<summary>What gets backed up</summary>

Most settings are backed up automatically, including:

* Your home screen layout, including icon positions and folders
* App drawer and search settings
* Most Lawnchair settings (gesture configurations, theme settings.)

</details>

<details open>

<summary>What is not included in a backup</summary>

* **Widgets**
  * The actual data or internal configuration of widgets is not saved. Only their placement on the home screen is recorded. Widgets will need to be reconfigured after a restore.
* **Third party apps**
  * Integrations that require third-party apps (such as icon packs, Smartspacer, etc.) will require their respective apps to work. If they are not installed, Lawnchair will use its default settings.
* **Work profile apps**
  * Due to inconsistencies in how Android handles work profiles, apps within a work profile may not restore reliably.
* **Apps not installed**
  * **I**f an app that was on your home screen or in your app drawer is not installed on the device you are restoring to, its icon will not appear.

</details>

To create a backup, follow these steps:

1. Navigate to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-cloud-plus">:cloud-plus:</i> **Create backup**.
3. On the screen that appears, adjust what to restore accordingly:
   * **Layout and settings**: Backs up everything noted above.
   * **Wallpaper**: Backs up your current wallpaper. This setting does not work if you have a live wallpaper.
4. Tap **Create**. You will be prompted to choose a name and location for your backup file.
   * We  recommend saving it to a location that is easily accessible storage (e.g., your device's Downloads folder, or a dedicated cloud drive folder).
   * The file will have a `.lawnchairbackup` extension (e.g., `Lawnchair_Backup January 01, 2026 00:00:00.lawnchairbackup`).

### Restoring a backup

Restoring applies a previously saved `.lawnchairbackup` file to your current Lawnchair installation.

To restore a backup, follow these steps:

1. Navigate to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-arrow-rotate-left">:arrow-rotate-left:</i> **Restore backup.**
3. On the screen that appears, find and select your backup file.
4. After selecting a backup, you can restore **Layout and settings**, **Wallpaper**, or both.
   * See the steps in Creating a backup for information on what gets restored.
5. Tap **Restore**.

### Restoring a Nova backup

If you are on Lawnchair 15 Beta 3 and above, Lawnchair offers a feature to import certain home screen settings from a Nova Launcher backup file (`.novabackup`).

This can help ease the migration for users switching from Nova Launcher.

<details>

<summary>What gets restored from a Nova backup</summary>

* Home screen grid layout (rows, columns)
* Icons and their positions
* Widgets and their positions (but not their internal data/settings)
* Folders and their contents (if apps are installed)
* Selected icon pack (if installed on the device)

</details>

<details>

<summary>What is <em>not</em> restored from a backup</summary>

* Any Nova-specific settings beyond the home screen layout (e.g., Nova gestures, notification badges)
* Subgrid layouts: items using them in Nova will be aligned to the nearest standard grid position
* App drawer layout, categories, or settings
* Lawnchair's own custom settings
* Apps not installed on your device

</details>

To restore a Nova backup:

1. Navigate to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-arrow-rotate-left">:arrow-rotate-left:</i> **Restore Nova backup.**
3. On the screen that appears, find and select your backup file.
4. A confirmation screen will appear, showing a summary of what will be restored.
   * If your Nova setup used subgrid positioning, you may see a warning indicating that items will be aligned to Lawnchair's standard grid.
   * You can optionally tap **Add extra row to show At a Glance** if you wish to show this feature.
5. Tap **Restore**.

### Reset settings to default

This action will revert Lawnchair to its factory default state. All your custom settings, including your home screen layout will be lost.

{% hint style="danger" %}
**Important:** This action is irreversible. Ensure you have created a backup if you wish to save your current setup before proceeding.
{% endhint %}

To reset Lawnchair's settings, follow these steps:

1. Navigate to **Home settings** > **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-circle-info">:circle-info:</i> **App info**.
3. On the screen that appears, tap **Storage and cache**.
4. Tap <i class="fa-trash-can">:trash-can:</i> **Clear storage**.
5. On the warning that appears, tap **Delete**.

### Troubleshooting issues

<details>

<summary>Can't find backup file</summary>

Check if the `.lawnchairbackup` file you are trying to restore is actually stored on your device's internal storage or an accessible cloud drive.

</details>

<details>

<summary>Can't restore the backup file</summary>

If your backup fails to restore, follow these steps:

* Ensure there are no unusual or unsupported characters in the `.lawnchairbackup` file's name. Try renaming the file to something simple (e.g., `backup.lawnchairbackup` ).
* Check if your backup file is downloaded in your phone.
* Ensure you are trying to restore a backup that is compatible with your currently installed Lawnchair version (e.g., don't try to restore a Lawnchair 16 backup to Lawnchair 15).
* Re-download or recreate the backup file if you suspect it's corrupted.

</details>
