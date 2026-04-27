---
description: Use QuickSwitch on rooted devices for better Recents integration.
icon: cards-blank
---

# QuickSwitch

[QuickSwitch](https://github.com/skittles9823/QuickSwitch) is a Magisk module that allows third-party launchers, like Lawnchair, to function as the system's Quickstep (Recents) provider.

It can improve gesture navigation, home animations, and Recents behavior.

{% hint style="warning" %}
**Important:** QuickSwitch requires **root access** on your device to function.

If your device is not rooted, this guide does not apply.
{% endhint %}

### How QuickSwitch works

QuickSwitch uses several components together:

* **Magisk Module**
  * This is the core component installed through your root solution.
  * It lets third-party launchers take over Recents.
* **QuickSwitch App**
  * This optional app gives you a simple UI for selecting the Recents provider.
  * It has its own Android version limits.
* **Lawnchair Quickstep support**
  * Lawnchair includes support for Recents, gestures, and system animations when QuickSwitch is active.

### Supported versions and devices

QuickSwitch support depends on your Android version and ROM.

### Prerequisites

* A **rooted Android device** (with Magisk, APatch, KernelSU, or a similar solution) installed and working.
* **Lawnchair** installed on your device.
* Magisk, KernelSU, or APatch installed.
* The **QuickSwitch Magisk Module** downloaded from the [official QuickSwitch releases page](https://github.com/skittles9823/QuickSwitch/releases).
  * If you are using APatch or KernelSU, download [this QuickSwitch fork](https://github.com/j7b3y/QuickSwitch) instead.

### Set up QuickSwitch

{% stepper %}
{% step %}
#### Install the Magisk module

1. Open the Magisk app (or equivalent root solution manager).
2. Go to the **Modules** section.
3. Tap **Install from storage** (or similar option).
4. Browse to and select the QuickSwitch `.zip` file you downloaded.
5. Allow the module to install.
6. **Reboot your device** when prompted.
{% endstep %}

{% step %}
#### Set Lawnchair as the default launcher

To set Lawnchair as your default launcher, follow the steps listed in [Install and setup](../getting-started/install-and-setup.md).
{% endstep %}

{% step %}
#### Choose Lawnchair as the Recents provider

Choose one of the methods below based on your Android version and root solution.

{% tabs %}
{% tab title="Method A: Via the app" %}
If you are running Android 13 and below, and use Magisk:

1. Open the **QuickSwitch app** (look for it in your app drawer).
2. In the app, choose **Lawnchair** from the list of available launchers.
3. The app will prompt you to **reboot your device**. Confirm and reboot.
{% endtab %}

{% tab title="Method B: Via a terminal command" %}
If you are running Android 14, using KernelSU or APatch, or if the app does not work, follow these steps:

1. Open a terminal emulator app on your device (e.g., Termux, or the terminal built into your root solution manager).
2. Launch a root shell (e.g., via `su`).
3.  Execute the following command:

    ```shellscript
    /data/adb/modules/quickswitch/quickswitch --ch=app.lawnchair
    ```
4. Reboot your device to apply the changes.
{% endtab %}
{% endtabs %}

After rebooting, Lawnchair should be handling system gestures and the Recents screen.
{% endstep %}
{% endstepper %}

### Troubleshooting QuickSwitch

<details>

<summary>QuickSwitch app not working on Android 14 or newer</summary>

The QuickSwitch app itself does not support Android 14 or above. You **must** use the terminal command method (Method B above) to activate Lawnchair as the Recents provider.

</details>

<details>

<summary>After activating QuickSwitch, Lawnchair crashes immediately, I get a black screen, or the system fails to boot reliably</summary>

This usually means QuickSwitch is not compatible with your current system setup.

* Your immediate priority is to disable the QuickSwitch module via your root solution's recovery mode and reboot your device.
* Once your system is stable, ensure you are using the latest version listed in [Choosing a version](../getting-started/choosing-a-version.md).
* If the issue persists, follow [Crashes](../troubleshooting/crashes.md) and mention QuickSwitch in your report.

</details>

<details>

<summary>After activation, I get a message saying <strong>Incompatible system integration</strong></summary>

This message appears when Lawnchair's Quickstep support cannot integrate with your system, even with QuickSwitch.

* Switch back to your system Quickstep provider.
* Ensure you are using the latest version listed in [Choosing a version](../getting-started/choosing-a-version.md).
* If no update fixes it, your device may not be fully compatible.
* Check the [Lawnchair issue tracker](https://github.com/LawnchairLauncher/lawnchair/issues) for similar reports.

</details>

<details>

<summary>I'm experiencing other issues with the QuickSwitch magisk module</summary>

If the QuickSwitch module itself is failing, report it on the [QuickSwitch issue tracker](https://github.com/skittles9823/QuickSwitch/issues).

</details>
