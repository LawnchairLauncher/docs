---
description: Understand launcher gesture limits and improve navigation behavior.
icon: hand-pointer
---

# Gesture navigation issues

Smooth gesture navigation is a big part of a good launcher experience.

On Android, results with third-party launchers can vary a lot by device, Android version, and OEM software.

{% hint style="info" %}
Gesture navigation on this page means _system navigation gestures_, not Lawnchair gestures under **Home settings** → **Gestures**.
{% endhint %}

### How does gesture navigation work?

Android gives the system launcher special privileges for handling home and Recents animations.

When you switch to a third-party launcher, those integrations may be less reliable.

### Common issues you might encounter

* Some OEMs, such as Xiaomi, block gesture navigation on custom launchers entirely
* Icons or widgets not responding for a short time after going home
* Home screen content flashing or disappearing when you tap icons too quickly after swiping home
* Home animations feeling choppy or not running at all
* App opening animations failing when you launch an app right after swiping home
* A short delay before the home screen content appears when swiping home
  * Oppo, OnePlus, and Realme introduced this issue on Android 14, but it can also appear elsewhere.

You may see some of these issues, all of them, or none of them.

### Options for improving gesture navigation

Many of these issues come from Android or OEM limits rather than Lawnchair itself. Here are the main ways to improve the experience.

#### For non-rooted users

On Android 11 and later, Lawnchair uses Google's `GestureNavContract` API to improve animations on non-rooted devices.

How well this works depends entirely on your device manufacturer.

* Devices close to stock Android, such as Pixel, Nothing, and AOSP-based ROMs, usually work better.
* Devices with heavily customized software, such as Samsung, Xiaomi, and OnePlus/Oppo, may still have major issues.

<details>

<summary>Icons are getting stuck on the screen after closing an app</summary>

A common bug causes an app icon to get stuck on screen after you close an app.

Google fixed this in Android 13, but some OEMs reintroduced it by modifying the API.

If this happens:

{% include "../.gitbook/includes/go-to-home-settings-more.md" %}

3. Tap <i class="fa-flask">:flask:</i> **Experimental features**.
4. Turn off **Use GestureNavContract API**.

</details>

#### For rooted users

If your device is rooted, the **QuickSwitch Magisk module** is usually the most effective option.

QuickSwitch allows Lawnchair to integrate as the system's Recents provider. This provides a more consistent animation experience.

See [QuickSwitch](../integrations/quickswitch.md) for setup details.
