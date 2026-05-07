# Get started

Read this page once you have decided to contribute code. It covers local setup and a realistic path to a small first contribution.

### Prerequisites

* [Android Studio](https://developer.android.com/studio/preview)
* Git
* At least 16 GB of RAM

macOS or Linux is recommended.

### Setup steps

1.  Clone the repository with the `--recursive` flag.

    ```bash
    git clone --recursive https://github.com/LawnchairLauncher/lawnchair.git
    ```
2. Open the project in Android Studio.
3. Select the `lawnWithQuickstepGithubDebug` build variant.

{% hint style="info" %}
If modules ending in `lib` fail to load, run `git submodule update --init --recursive`.
{% endhint %}

### Creating your first contribution

{% stepper %}
{% step %}
#### Pick your first change

1. Pick a bug that affects you or a very small feature.
2. Prefer changes you can explain in one sentence.
3. Avoid broad refactors or multi-area rewrites for your first PR.

Check the [issue tracker](https://github.com/LawnchairLauncher/lawnchair/issues) before you start. If your bug or idea is not listed, consider opening an issue first.

If you are unsure whether a change is a good fit, ask in the [community channels](https://app.gitbook.com/s/6t9zDE3woL9vF6pobrxs/get-involved/community-channels) before writing code.
{% endstep %}

{% step %}
#### Open your first PR

1. Make your change in a new branch.
2. Test it in a debug build on a device or emulator.
3. Open a [pull request on GitHub](https://github.com/LawnchairLauncher/lawnchair/pulls).
4. Follow the PR template and explain what changed.

{% hint style="info" %}
Reviews can take anywhere from a day to several weeks. The project is maintained by a small volunteer team. If your PR has no activity after two weeks, a gentle ping is fine.
{% endhint %}

If review feedback comes in, try to address it with small follow-up commits. If you get stuck, ask for clarification or close the PR and come back later.
{% endstep %}
{% endstepper %}
