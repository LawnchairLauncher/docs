---
description: Allow restricted settings for sideloaded Lawnchair builds on Android 13+.
icon: lock
---

# Restricted settings

On Android 13 and later, some sensitive permissions are blocked by default for apps installed outside Google Play.

This includes permissions such as notification access and accessibility services.

To use these features in Lawnchair, you may need to allow restricted settings for the app.

{% hint style="info" %}
This is usually only required for sideloaded **GitHub** and **Nightly** builds. It is usually not needed for the Play Story builds.
{% endhint %}

### Allow restricted settings for Lawnchair

{% stepper %}
{% step %}
### Trigger the restricted setting message

Try to turn on a setting that needs restricted access, such as an accessibility service.

You must see the **Restricted setting** message for the next steps to work correctly.
{% endstep %}

{% step %}
### Grant the requested permission

1. Open **Home settings**.
2. Tap **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i> > **App info**.
3. On Lawnchair's **App info** screen, tap **More** <i class="fa-ellipsis-vertical">:ellipsis-vertical:</i>.
4. Tap **Allow restricted settings**.
5. Follow the on-screen instructions.
{% endstep %}
{% endstepper %}

For more details, see [Google's support page for restricted settings](https://support.google.com/android/answer/12623953#allowrestrictedsettings).
