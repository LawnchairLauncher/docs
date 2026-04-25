# Get started

### Requirements

1. [Android Studio](https://developer.android.com/studio/preview)
2. Git
3. At least 16 GB of RAM

MacOS or Linux is recommended for building Lawnchair.

### Setup steps

1.  Clone the repository with the `--recursive` flag to include the project's submodules.

    ```bash
    git clone --recursive https://github.com/LawnchairLauncher/lawnchair.git
    ```
2. Open the project in Android Studio.
3. Select the `lawnWithQuickstepGithubDebug` build variant.

If you encounter errors with modules that ends with `lib` suffix like `iconloaderlib` or `searchuilib`, run `git submodule update --init --recursive`.

