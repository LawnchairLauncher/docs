# Installation issues

There are several reasons why Android might block installation of Lawnchair, especially when sideloading an APK file when using the GitHub or Nighlty versions.

### Play Protect blocking installation

Google Play Protect is a security feature on Android devices designed to scan apps for potential harm. Sometimes, when you install an app from outside the Play Store (like Lawnchair's GitHub or Nightly versions), Play Protect might display a warning or block the installation, even for trusted apps.

To work around this issue, follow these steps:

1. When prompted by Play Protect, tap **Install anyway**.
2. If installation is blocked without this option:
   1. Open the Play Store app.
   2. Tap your profile icon.
   3. Tap **Play Protect**, then tap **Settings** <i class="fa-gear">:gear:</i>.
   4. Tap **Scan apps with Play Protect.**
   5. On the message that appears, tap **Pause** or **Turn off**.
   6. Install Lawnchair.
   7. Once installation is complete, immediately turn on Play Protect to keep your device secure.

### "App not installed" error

This is a generic Android error message that can have several causes when sideloading from an APK file.

<details>

<summary>Check if you downloaded from an official source</summary>

You might have downloaded an APK file that has been modified or originates from an unofficial source. These often have different digital signatures that prevent installation.

**Solution:** Always download from an official source, as outlined in [choosing-a-version.md](../getting-started/choosing-a-version.md "mention").

</details>

<details>

<summary>Check your downloaded file</summary>

The APK file you downloaded might be incomplete or damaged.

**Solution:** Delete the APK file you have, then download it again.

</details>

<details>

<summary>Check your Lawnchair version</summary>

You might be trying to install an older version of Lawnchair on top of a newer version of Lawnchair, especially when using Nightly builds.

**Solution:** You must first uninstall the newer version of Lawnchair from your device before installing the older one.

</details>

