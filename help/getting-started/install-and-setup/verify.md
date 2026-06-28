---
hidden: true
---

# Verify your installation

Lawnchair's APKs are cryptographically signed. You can verify the integrity and authenticity of your downloaded files using two systems:

* GitHub / SLSA attestations (available starting with Lawnchair 15 Beta 1)
* SHA-256 Android app certificate fingerprints

### SLSA attestation

Every Lawnchair release starting with Lawnchair 15 Beta 1 (excluding Nightly builds) is attested and verified with SLSA provenance. This repository meets the requirements for SLSA Level 2 compliance.

{% hint style="info" %}
You can verify the installation without using the GitHub CLI by cross-referencing checks from [GitHub Attestations](https://github.com/LawnchairLauncher/lawnchair/attestations) with [Sigstore Rekor](https://search.sigstore.dev/).
{% endhint %}

To verify using the GitHub CLI:

1. Install the [GitHub CLI](https://cli.github.com/).
2. Download the APK and its corresponding attestation from [GitHub Attestations](https://github.com/LawnchairLauncher/lawnchair/attestations).
3.  Run the following command in your terminal, replacing `{APK}` with the path to your downloaded APK file:

    ```bash
    gh attestation verify {APK} -R LawnchairLauncher/lawnchair
    ```

### Android app certificate

Lawnchair uses two distinct app certificates depending on where the app was downloaded. You can verify these certificates using tools such as [AppVerifier](https://github.com/soupslurpr/AppVerifier).

{% tabs %}
{% tab title="Play Store version" %}
```
47:AC:92:63:1C:60:35:13:CC:8D:26:DD:9C:FF:E0:71:9A:8B:36:55:44:DC:CE:C2:09:58:24:EC:25:61:20:A7
```
{% endtab %}

{% tab title="GitHub version" %}
```
74:7C:36:45:B3:57:25:8B:2E:23:E8:51:E5:3C:96:74:7F:E0:AD:D0:07:E5:BA:2C:D9:7E:8C:85:57:2E:4D:C5
```
{% endtab %}
{% endtabs %}
