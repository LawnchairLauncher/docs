# Gesture navigation issues

Smooth gesture navigation is important for a great home screen experience.

However, its behavior with third-party launchers like Lawnchair can vary significantly based on your phone's manufacturer (OEM), their specific version of Android, and other software customizations.

{% hint style="info" %}
Gesture navigation in this page refers to **system navigation via gestures**, not Lawnchair's home screen gestures found at Home settings > Gestures.
{% endhint %}

### How does gesture navigation work?

Android is designed with system launcher having special privileges for handling gesture animations (like swiping home or accessing the Recents screen).

When you switch to a third-party launcher, these integrations might not be as seamless.

### Common issues you might encounter

* Some OEMs like Xiaomi block gesture navigation on custom launchers entirely
* Not being able to tap icons or widgets for a short time after going home
* Home screen content flashing or disappearing entirely when tapping icons quickly after swiping home
* Home animations not being as fluid as expected or completely non-existent
* Opening animations not working when quickly opening an app after swiping home
* A short delay before the home screen content appears when swiping home
  * Oppo (therefore OnePlus and Realme) introduced this issue with their Android 14 update but it may also be present on other devices and versions.

This list might not include every possible issue, and you may experience some or none of the issues here.

### Options for improving gesture navigation

While many issues are caused by system-level limitations beyond Lawnchair's direct control, here are the main approaches to managing your gesture experience.

#### For non-rooted users

Lawnchair uses Google's official `GestureNavContract` API (on Android 11+) to improve animation smoothness for non-rooted devices.

The effectiveness of this API is **entirely dependent on how well your device manufacturer has implemented it**.

* Devices with software close to stock Android (like Google Pixel, Nothing Phone, or phones running AOSP-based custom ROMs) generally have better results.
* Devices with heavily customized software (e.g., from Samsung, Xiaomi, or OnePlus/Oppo) may still experience significant issues.

<details>

<summary>Icons are getting stuck on the screen after closing an app</summary>

A common bug, where an app's icon gets stuck on the screen after closing an app, was initially fixed by Google in Android 13.

However, this issue has reappeared on some OEM devices (e.g., Samsung on Android 15+ One UI 6) that have modified the API.

To manage this, follow these steps:

1. Navigate to **Home settings**, then tap More<i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
2. Tap <i class="fa-flask">:flask:</i> **Experimental features**.
3. Turn off **Use GestureNavContract API**.

</details>

#### For rooted users

If your device is rooted, using the **QuickSwitch Magisk module** is highly recommended.

QuickSwitch allows Lawnchair to integrate as the system's Recents provider. This provides a more consistent animation experience.

Refer to our [QuickSwitch integration page](../integrations/quickswitch.md) for more details.

