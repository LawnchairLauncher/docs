# QuickSwitch

[QuickSwitch](https://github.com/skittles9823/QuickSwitch) is a Magisk module that allows third-party launchers, like Lawnchair, to function as the system's Quickstep (Recents) provider.

This integration provides a significantly smoother gesture navigation experience, more fluid animations when returning to the home screen, and access to enhanced Recents screen features.

{% hint style="warning" %}
**Important:** QuickSwitch requires **root access** on your device to function.

&#x20;If your device is not rooted, this guide does not apply to you.
{% endhint %}

### Components of QuickSwitch

QuickSwitch is not a single app; it involves several components working together:

* **Magisk Module**
  * This is the core component installed via your root solution (like Magisk). It modifies the system to allow third-party launchers to take over Recents.
* **QuickSwitch App**
  * A separate app designed to provide a user-friendly interface for selecting which launcher should act as the Recents provider. This app has its own Android version limitations.
* **Lawnchair's QuickStep support**
  * Lawnchair includes its own code that enables it to communicate with the QuickSwitch module and handle system Recents, animations, and gestures.

### Supported versions and devices

QuickSwitch support can vary depending on your device's Android version and specific ROM.

* A **rooted Android device** (with Magisk, APatch, KernelSU, or a similar solution) installed and working.
* **Lawnchair** installed on your device.

### Prerequisites

* A **rooted Android device** (with Magisk, APatch, KernelSU, or a similar solution) installed and working.
* **Lawnchair** installed on your device.
* Magisk, KSU, or Apatch must be installed.
* The **QuickSwitch Magisk Module** downloaded. You can find the latest release on its [official GitHub repository](https://www.google.com/url?sa=E\&q=https%3A%2F%2Fgithub.com%2Fskittles9823%2FQuickSwitch%2Freleases).
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

To set Lawnchair as your default launcher, follow the steps listed in "Install and setup":

{% content-ref url="../getting-started/install-and-setup.md" %}
[install-and-setup.md](../getting-started/install-and-setup.md)
{% endcontent-ref %}
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
If you are running Android 14, using KernelSU or Apatch, or if the app does not work, follow these steps:

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

This indicates a severe incompatibility or issue with QuickSwitch on your specific system, or with how Lawnchair is interacting with it.

* Your immediate priority is to disable the QuickSwitch module via your root solution's recovery mode and reboot your device.
* Once your system is stable, ensure you are [running the latest version of Lawnchair](../getting-started/choosing-a-version.md).
* If the issue persists with the latest version, please follow our guide on [troubleshooting crashes](../troubleshooting/crashes.md) and submit a detailed report, explicitly mentioning QuickSwitch.

</details>

<details>

<summary>After activation, I get a message saying <strong>Incompatible system integration</strong></summary>

Tis message appears if Lawnchair's Quickstep support cannot properly integrate with your device's system, even with QuickSwitch.&#x20;

* Switch back to your system's QuickStep provider via [the steps above](quickswitch.md#set-lawnchair-as-the-default-launcher).
* If there are no updates available. You must change your QuickStep provider to use system.
* Ensure you are [running the latest version of Lawnchair](../getting-started/choosing-a-version.md). If no updates are available, your device may simply not be fully compatible. You can check our [issue tracker](https://app.gitbook.com/s/6t9zDE3woL9vF6pobrxs/get-involved/report-issues) for similar reports.

</details>

<details>

<summary>I'm experiencing other issues with the QuickSwitch magisk module</summary>

If you encounter problems with the QuickSwitch module itself (e.g., issues with other launchers, module failing to install), you can report them on the [QuickSwitch module's GitHub issue tracker](https://github.com/skittles9823/QuickSwitch/issues).

</details>





