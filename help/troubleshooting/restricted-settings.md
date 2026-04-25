# Restricted settings

On devices running Android 13 and newer, certain app permissions, like notification access and accessibility services, are blocked by default for apps installed outside the Google Play Store.

This is a security feature designed by Android to protect your device.

To use certain features in Lawnchair that require these sensitive permissions, you may need to manually grant restricted settings access to Lawnchair.

{% hint style="info" %}
This step is usually only required for the **GitHub and Nightly versions** that are sideloaded. It is generally not needed for the Play Store versions.
{% endhint %}

### Allow restricted settings for Lawnchair

{% stepper %}
{% step %}
### Trigger the restricted setting message

Attempt to turn on a setting that requires restricted access (e.g., accessibility services).

You must see the **Restricted setting** message for the next steps to work correctly.
{% endstep %}

{% step %}
### Grant the requested permission

1. Open **Home settings.**
2. Tap **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i> > **App info**.
3. On Lawnchair's **App info** screen, tap **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
4. Tap **Allow restricted settings**.
5. Follow the on-screen instructions.
{% endstep %}
{% endstepper %}

For more information about restricted settings in Android, refer to [Google's official support page](https://support.google.com/android/answer/12623953#allowrestrictedsettings).



