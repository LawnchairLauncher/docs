---
description: Capture crash logs and try the fastest recovery steps.
icon: bug
---

# Crashes

If Lawnchair crashes, you can usually capture a report and share it with the team.

### How Lawnchair handles crash reports

Lawnchair includes automatic crash reporting.

When the app crashes, you will usually get a notification that lets you generate a shareable crash log link.

{% hint style="warning" %}
On Android 14 and newer, you must have **notifications** turned on for Lawnchair to receive these crash reports.
{% endhint %}

### How to capture and report a crash

1. When you see the Lawnchair crash notification, tap **Upload file**.
2. A unique link to the crash log will be generated. Tap **Copy to clipboard**.
3. Report the crash on GitHub:
   1. Navigate to our [GitHub bug report form](https://github.com/LawnchairLauncher/lawnchair/issues/new?template=bug_report.yaml).
   2. Follow the steps in the form.
      1. In the "Additional Information" section of the form, paste the crash log link you copied in step 2.
   3. Submit the form.

### Basic troubleshooting steps for frequent crashes

If Lawnchair is crashing frequently, try these general steps:

<details>

<summary>Restart Lawnchair</summary>

{% include "../.gitbook/includes/restart-lawnchair.md" %}

</details>

<details>

<summary>Clear the app cache</summary>

1. Open **Home settings**.
2. Tap **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
3. Tap **App info**.
4. Open **Storage and cache**.
5. Tap **Clear cache**.

</details>

<details>

<summary>Restart your device</summary>

1. On most phones, press your phone's power button for about 30 seconds, or until your phone restarts.
2. If prompted, tap **Restart** <i class="fa-repeat">:repeat:</i>.

</details>

<details>

<summary>Consider resetting Lawnchair to its default settings</summary>

**Important:** Resetting Lawnchair removes your custom settings and layout.

Before you do this, create a backup.

See [Backup, restore, and reset](../core-features/backup-restore-and-reset.md).

</details>
