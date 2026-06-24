# Lawnchair documentation source

This directory contains the raw Markdown source files for Lawnchair's official documentation, hosted at [docs.lawnchair.app](https://docs.lawnchair.app).

### GitBook synchronization

We use bidirectional synchronization between this directory and GitBook. 

* **GitHub to GitBook:** Merging a Pull Request that modifies files in this directory will automatically update the live documentation site.
* **GitBook to GitHub:** Edits made directly on the GitBook web interface are automatically committed and pushed back to the `16-dev` branch of this repository.

To prevent merge conflicts, ensure your local branch is fully up-to-date with the remote repository before making any edits.

### Contributing to the documentation

Before making any changes to these files, please read our official [Writing documentation guide](https://docs.lawnchair.app/community/get-involved/writing-documentation). It outlines our strict formatting rules, sentence case requirements, and tone guidelines.

### Navigation and sidebar

The sidebar navigation structure of the documentation site is defined by the `SUMMARY.md` file in this directory. If you add a new page, you must register it in `SUMMARY.md` for it to appear in the navigation menu.