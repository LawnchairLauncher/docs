# Lawnchair Documentation Style Guide

This guide outlines the conventions for writing and maintaining Lawnchair's documentation. Adhering to these principles ensures consistency, clarity, and a positive user and contributor experience.

## I. Core Principles (Derived from Diátaxis Framework & Project Directives)

*   **Audience-Centric:** Always write for the primary audience of the specific document (End-User, Developer, Community Member). Content must be relevant and accessible to them.
*   **Friction Reduction:** The documentation's overarching goal is to reduce confusion and accelerate task completion for its audience.
*   **Single Source of Truth (SSOT):** Avoid duplicating information across multiple pages or sources. If information is needed in multiple places, link to the authoritative source.
*   **Necessity Only:** Only document features or processes that are genuinely confusing, non-obvious, or require specific multi-step setup. Avoid documenting truly self-explanatory UI elements.
*   **Transparency & Factual Neutrality:** Present facts objectively. Acknowledge limitations, known issues, and external dependencies honestly. Avoid marketing language or making unfulfillable promises.

## II. Tone of Voice

*   **Empathetic Authority:**
    *   **Empathetic:** Acknowledge user frustrations and pain points (e.g., crashes, gesture issues) without being apologetic for external system limitations. Validate their experience.
    *   **Authoritative:** Be direct, clear, and confident in the information provided. Speak as an expert guide.
*   **Concise & Direct:** Get straight to the point. Maximize value per character. Avoid verbose explanations or fluff.
*   **Respectful:** Maintain a civil and respectful tone towards users, contributors, and other projects/OEMs, even when discussing their limitations.

## III. Language & Terminology

*   **User-First Language (User Guide Specific):**
    *   **Prefer:** "Turn on," "Turn off," "Show," "Hide," "Toggle," "Adjust," "Set up," "Use," "Settings," "Option," "Feature."
    *   **Avoid:** "Enable," "Disable," "Activate," "Deactivate," "Functionality," "Implement," "Utilize," "Configuration," "Parameter."
*   **Consistent Nomenclature:**
    *   **Lawnchair Versions:**
        *   **Lawnchair (GitHub Version):** For `app.lawnchair` package (Official Beta, website, Discord, Telegram, APKMirror).
        *   **Lawnchair (Play Store Version):** For `app.lawnchair.play` package (Google Play Store).
        *   **Lawnchair (Nightly Version):** For `app.lawnchair.nightly` package.
    *   **UI Elements:** Use the exact text displayed in the Lawnchair UI or Android system settings.
*   **Technical Jargon:**
    *   **User Guide:** Avoid technical jargon. If a technical term is unavoidable, provide a simple, plain-language explanation or an analogy.
    *   **Developer Guide:** Technical jargon is appropriate and expected.

## IV. Formatting & Structure

*   **Headings:**
    *   Use **Sentence case** for all page titles and section headings (e.g., `# Getting Started`, `### How to use Lawnicons`). Exceptions are for proper nouns/brands (e.g., `GestureNavContract`).
    *   Use Markdown heading levels (`#`, `##`, `###`) consistently to reflect hierarchy.
*   **Emphasis:**
    *   **Bold Text:** Reserve bold primarily for **UI elements** (e.g., button names, setting options like **Home settings > General**), or for very short, critical warnings/labels (e.g., "**Important:**").
    *   **Avoid bold in non-UI text.** Too much bold text is overwhelming and diminishes the impact of actual emphasis.
*   **Lists:**
    *   Use numbered lists for sequential steps in a process (How-To Guides).
    *   Use bulleted lists for non-ordered items, features, considerations, or troubleshooting checklists.
*   **Code Blocks:**
    *   Use code blocks for terminal commands, code snippets, or specific file contents.
*   **Hints/Notes/Warnings:**
    *   Use GitBook's `{% hint style="info" %}`, `{% hint style="warning" %}`, etc., for important call-out boxes, tips, or caveats.
*   **Navigation Paths:**
    *   Use the `>` symbol as a standard separator for navigation paths (e.g., `Home settings > More > App info`).
    *   Use `More` to refer to the vertical three-dots menu icon `⋮`.
*   **External Links:**
    *   Provide clear, descriptive links to external resources (e.g., GitHub repositories, official documentation, `dontkillmyapp.com`).
    *   Do not link to Lawnchair's internal issue tracker from general user-facing troubleshooting pages unless specifically for reporting *new, unlisted* issues.

## V. Documentation Workflow

*   **Dump, Refine, Connect:**
    1.  **Dump (Archivist):** Quickly get raw content onto pages without editing. Overcome blank page inertia.
    2.  **Refine (Writer/Editor):** Edit each page individually for clarity, structure, and adherence to style.
    3.  **Connect (Architect):** Add cross-links between related pages to create a cohesive knowledge base.
*   **Documentation as Part of Development:** Link documentation updates to the Pull Request process for new features or bug fixes. A feature is not "done" until its documentation is updated.
*   **Regular Review:** Periodically review documentation for accuracy, relevance, and consistency.