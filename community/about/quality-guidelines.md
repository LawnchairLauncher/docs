# Contribution quality guidelines

These guidelines define the minimum standards expected for contributions to the Lawnchair project.

Lawnchair does not require contributors to use or avoid any particular development tools. Contributors may use these when they find them helpful, provided that the resulting contribution meets these guidelines.

**You are responsible for everything you submit to the Lawnchair project.**

Contributions that are lazy, unverified, unchecked, or otherwise fail to meet these standards will have their issue or pull request closed.

### Write messages for humans

All human-facing text must be reviewed and finalized by you, the contributor.

Tools may be used to assist with brainstorming, editing, or improving clarity, but you are responsible for ensuring that anything you post is accurate and relevant for the context.&#x20;

This applies to issue or PR descriptions, commit messages, replies during code reviews, and other forms of communication where a human is expected to read.

For specific guidelines, view the list below:

* **Issue or PR descriptions**
  * Write clear, concise, and direct explanations for your changes.
  * Do not explain the changes you made in a verbose matter. This includes writing what you changed for each file, long explanations as to why you made this PR, and excessive use of markdown formatting.&#x20;
* **Code comments**
  * Comments must be sparse, precise, and human-written. If code is well-written, it should be self-explanatory.
  * Do not write verbose comments explaining what the code does. A useful guide for writing comments can be found at [this StackOverflow blog](https://stackoverflow.blog/2021/12/23/best-practices-for-writing-code-comments/).
* **Maintainer replies**
  * When responding to maintainer feedback, write your own replies.
  * Do not use tools to post boilerplate or irrelevant responses.

### Test your changes

All changes submitted to the repository must be tested on a real device or emulator. This especially applies to changes that affect any part of the UI.

Simply running `./gradlew app:assembleLawnWithQuickstepGithubDebug spotlessLint`  is not enough for testing, especially for major refactors or UI changes.

As such, all pull requests containing UI changes must include visual proof (such as screenshots or GIFs, preferably videos) written in the Testing section of the PR description.

If a PR that changes the UI does not contain visual proof of manual testing, it will be marked as `status: needs info` or closed.

### Adhere to project standards

Contributors are expected to ensure that their changes fit within the existing code architecture and project conventions. Tools may suggest generic solutions or external dependencies that do not align with our codebase.

You must ensure that the code you wrote fits within our code architecture and does not implement any [rejected-features.md](rejected-features.md "mention").

Specifically:

* **Do not reinvent the wheel**
  * Before writing custom helpers, UI components, or importing dependencies, check if Lawnchair already has an established way to do this.
  * Always prefer project standards (such as the version checks in `Utilities` ) over alternatives.
* **Keep changes to AOSP minimal**
  * If you are modifying anything outside the `lawnchair` module, keep your changes strictly minimal to prevent issues during future Android version rebases.
  * If possible, use hooks, dependency injection, or subclassing rather than modifying core files directly.
  * When writing code in Launcher3, prefer offloading your changes in a new file in the `lawnchair`  module, and calling your specific changes in the Launcher3-specific files.

### Own your contributions

You are the author of your PR. If you use any automated tools to write code, you are responsible for reviewing, testing, and fully understanding the code you submit.

This includes being able to explain the technical necessity and behavior of your changes during code review.

If a reviewer asks you to explain a specific code block in your PR and you cannot do so, the PR will be closed.

#### Oversee automated contributions

Automated tools must not independently create issues or pull requests, post comments, respond to code review feedback, or otherwise interact with project maintainers or community members without meaningful human oversight.

Contributors are responsible for reviewing automated output before it is submitted or posted.

Lawnchair may restrict or reject automated activity that creates excessive review, moderation, or maintenance burden.
