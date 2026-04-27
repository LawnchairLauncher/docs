---
description: Show Google Discover on the left of your home screen.
icon: newspaper
---

# Google Feed

The **Google Feed**, also called **Google Discover**, shows personalized news, articles, and updates from Google.

When turned on in Lawnchair, it appears as a dedicated page to the left of your home screen.

### Prerequisites

To use Google Feed, you may need an extra app depending on your Lawnchair version:

* **Nightly**: Feed support is usually built in.
* **Other versions**: Download and install [Lawnfeed 4](https://lawnchair.app/downloads).
  * If Lawnfeed 4 does not work, try [AIDL Bridge](https://github.com/amirzaidi/AIDLBridge/releases) instead.

### Show the Google Feed in Lawnchair

1. Go to **Home settings** → **Home screen**, then turn on **Show feed**.
2. Make sure **Feed provider** is set to Google. This uses Lawnfeed 4, if installed, or the built-in integration on Nightly.
   * If you installed AIDL Bridge, change the feed provider to use **AIDL Bridge**.
3. Once selected, swipe left to show the feed.

### Common issues

<details>

<summary>Google Feed does not show up</summary>

If Google Feed does not appear or does not work correctly, try these steps:

1. Toggle the **Show feed** setting on and off.
2. Force stop the Google app, then restart Lawnchair.
3. Restart your device.

</details>

<details>

<summary>Google Feed still doesn't work</summary>

On some devices, Lawnfeed may not connect to Google Feed reliably.

If you've tried the above steps and still experience problems, consider using AIDL Bridge as your feed provider instead:

1. Ensure AIDL Bridge is installed.
2. Go to **Home settings** → **Home screen**.
3. Tap **Feed provider**, then select **AIDL Bridge** from the list.

</details>
