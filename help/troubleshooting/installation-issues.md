# Installation issues

Android can block Lawnchair installation for a few common reasons.

This usually happens when you sideload an APK from the GitHub or Nightly release channels.

### Play Protect blocking installation

Google Play Protect scans apps for potential harm.

When you install Lawnchair from outside the Play Store, Play Protect may warn you or block the install.

To continue:

1. When prompted by Play Protect, tap **Install anyway**.
2. If installation is blocked without this option:
   1. Open the Play Store app.
   2. Tap your profile icon.
   3. Tap **Play Protect**, then tap **Settings** <i class="fa-gear">:gear:</i>.
   4. Tap **Scan apps with Play Protect**.
   5. On the message that appears, tap **Pause** or **Turn off**.
   6. Install Lawnchair.
   7. Turn Play Protect back on as soon as installation finishes.

### "App not installed" error

This is a generic Android error with several possible causes when you sideload an APK.

<details>

<summary>Check if you downloaded from an official source</summary>

You might have downloaded an APK file that has been modified or originates from an unofficial source. These often have different digital signatures that prevent installation.

**Solution:** Download Lawnchair from an official source listed in [Choosing a version](../getting-started/choosing-a-version.md).

</details>

<details>

<summary>Check your downloaded file</summary>

The APK file you downloaded might be incomplete or damaged.

**Solution:** Delete the APK, then download it again.

</details>

<details>

<summary>Check your Lawnchair version</summary>

You might be trying to install an older version over a newer one, especially with Nightly builds.

**Solution:** Uninstall the newer version first, then install the older one.

</details>
