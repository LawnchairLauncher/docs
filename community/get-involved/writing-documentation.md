# Writing documentation

This page outlines the conventions and workflows for contributing to Lawnchair's documentation. Following these guidelines ensures that our documentation remains accurate, scannable, and easy to maintain.

## Documentation philosophy

Our documentation is divided into distinct guides, each serving a specific audience. When writing or editing, you must adhere to the core philosophy of that section:

* User guide (inverted pyramid): users are often frustrated when they open documentation. Front-load the solution with a one-sentence TL;DR, then provide clear step-by-step instructions. Keep deeper technical explanation near the end.
* Developer guide (principles over code): code changes often, but architecture and contracts are more stable. Focus on constraints, interfaces, and expectations instead of volatile implementation details.
* Community guide (direct action): keep pages short and focused on a clear next step, such as contributing on GitHub, translating on Crowdin, or donating.

## How to contribute

Lawnchair's documentation is hosted on GitBook but is managed entirely through our GitHub repository. To maintain a single, consolidated review process, all changes must be submitted as Pull Requests on GitHub.

1. Clone the repository and open the directory that contains the page you want to update.
2. Edit the Markdown files directly.
3. If you add a new page, register it in `SUMMARY.md` so it appears in sidebar navigation.
4. Open a Pull Request targeting the `main` branch. After merge, changes sync to GitBook automatically.

Important: avoid platform-specific GitBook blocks or plugins that do not render correctly in standard Markdown viewers, including GitHub.

## Style and formatting

To maintain visual consistency across all pages, adhere to the following rules:

* Headings: use sentence case for page titles and section headings. Avoid symbols and questions in headings.
* Bold text: use bold only for UI labels or short critical warnings.
* Navigation paths: use the `>` separator (example: Home settings > General > Icon style).
* More icon: refer to the vertical three-dots menu icon `⋮` as More.
* Terminology: in user-facing pages, prefer plain language. For example, use "turn on" instead of "enable" and "search bar" instead of "QSB."

## Adding visual media

Visuals are highly effective for reducing cognitive load on frustrated users.

* Screenshots and GIFs: use these for complex setup and troubleshooting flows.
* Storage: store media files in `/docs/assets/`.
* Linking: use relative paths (example: `../assets/restricted-settings-step1.png`) so assets render on both GitHub and GitBook.