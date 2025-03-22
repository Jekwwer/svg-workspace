# Style Guide

This document outlines the style guide for **Jekwwer/svg-workspace**.
It covers commit message formatting, coding conventions, repository structure,
and other aspects detailed in [Scope][SCOPE].
Adhering to these guidelines ensures a consistent and readable project.

## Introduction

### Purpose

This guide standardizes coding and documentation practices to ensure consistency, enhance readability,
and support effective collaboration.

### Audience

This style guide is intended for:

- **Developers and Contributors:** Those writing code or documentation for the project.
- **Maintainers:** Individuals responsible for reviewing and merging contributions.
- **Reviewers:** Participants in code reviews to ensure adherence to standards.

### Scope

This document covers:

- **Repository Structure:** Directory layout, file naming conventions, and configuration file details.
- **Naming Conventions:** Standards for variables, constants, functions, and file/directory names.
- **Code Formatting and Style:** Guidelines on indentation, line length, brace styles, comments, EditorConfig settings,
  and linting/formatting tools.
- **Documentation:** Standards for creating and maintaining project documentation.
- **Additional Best Practices:** Other practices to improve overall code quality and project maintainability.

## Project Overview

### Project Goals

This repository provides a ready-to-use development environment for SVG files, leveraging devcontainer technology
and GitHub Codespaces with VS Code.

### Technology Stack

Primarily VS Code configurations, devcontainer setup, and essential extensions.

### Target Audience

Developers who need a streamlined workspace template for SVG development only.

## Repository Structure

### Directory Layout

```plaintext
/ (root)                                        # repository root
├── .devcontainer                               ├── # devcontainer-related configurations
│   └── devcontainer.json                       │   └── # devcontainer setup
├── .github                                     ├── # GitHub-related configurations
│   ├── ISSUE_TEMPLATE                          │   ├── # issue templates
│   │   └── *                                   │   │   └── # all files in the folder
│   ├── PULL_REQUEST_TEMPLATE                   │   ├── # pull request templates
│   │   └── *                                   │   │   └── # all files in the folder
│   ├── workflows                               │   ├── # GitHub workflows
│   │   └── release.yml                         │   │   └── # release workflow
│   ├── dependabot.yml                          │   ├── # Dependabot configuration
│   ├── FUNDING.yml                             │   ├── # funding configuration
│   └── PULL_REQUEST_TEMPLATE.md                │   ├── # default pull request template
├── .editorconfig                               ├── # editor configuration
├── .gitignore                                  ├── # files to ignore in Git and markdown linting
├── .markdownlint.json                          ├── # markdown linting configuration
├── .pre-commit-config.yaml                     ├── # pre-commit hook configuration
├── .prettierrc                                 ├── # Prettier configuration
├── .releaserc.js                               ├── # semantic release configuration
├── CHANGELOG.md                                ├── # changelog
├── CODE_OF_CONDUCT.md                          ├── # code of conduct
├── CONTRIBUTING.md                             ├── # contributing guidelines
├── cspell.json                                 ├── # spell checking configuration
├── LICENSE                                     ├── # MIT license
├── package-lock.json                           ├── # npm lock file
├── package.json                                ├── # npm package configuration
├── README.md                                   ├── # project README
├── SECURITY.md                                 ├── # security information
└── STYLEGUIDE.md                               └── # style guide
```

### File Naming Conventions

- **Documentation Files:**
  Key documentation files (e.g., `CODE_OF_CONDUCT.md`, `CONTRIBUTING.md`, `README.md`, `SECURITY.md`) are named using
  **SCREAMING_SNAKE_CASE**.

- **Configuration Files:**
  Tool configuration files (e.g., `cspell.json`, `.editorconfig`, `.pre-commit-config.yaml`,`.prettierrc`)
  use lowercase naming, following the specific requirements of each tool.

- **Scripts:**
  Executable scripts are named in lowercase, typically using **snake_case** for clarity and consistency.

- **GitHub and Workflow Files:**
  Files within the `.github` directory—such as `dependabot.yml`, `FUNDING.yml`,
  and templates under `ISSUE_TEMPLATE`/`PULL_REQUEST_TEMPLATE` follow GitHub's naming conventions.
  This may include a mix of uppercase (e.g., `BUG_REPORT.md`) and lowercase (e.g., `config.yml`) filenames
  to ensure proper GitHub integration.
  In the `.github/workflows/` directory, YAML files for GitHub Actions are recommended to use kebab-case
  (e.g., `deploy-app.yml`, `run-tests.yml`), aligning with GitHub's documentation and best practices.

### Directory Naming Conventions

- **General Naming:**
  Use lowercase letters for directory names. For multi-word names, use **kebab-case**
  (e.g., `node-modules`, `source-files`). Choose names that clearly indicate the directory's content or purpose
  (e.g., `docs` for documentation, `assets` for media).

- **Special Directories:**
  Directories prefixed with a dot (e.g., `.github`, `.devcontainer`) have specific roles and should remain unchanged.

### Configuration Files

Key configuration files in the repository include:

- `.gitignore`: Specifies files and directories to exclude from version control and Markdown linting.
- `.editorconfig`: Defines coding styles across editors.
- `.markdownlint.json`: Configures Markdown linting rules.
- `.pre-commit-config.yaml`: Specifies pre-commit hooks.
- `.prettierrc`: Contains formatting rules.
- `.releaserc.js`: Configures the semantic release process and versioning.
- `cspell.json`: Sets spelling rules for consistency.
- `package.json`: Contains project metadata, scripts, and dependency definitions.
- `package-lock.json`: Locks dependency versions to ensure consistent installations.

## Naming Conventions

### General Guidelines

Be descriptive and consistent with all naming choices to maintain clarity and uniformity across the project.

### IDs and Classes

Use **kebab-case** for all IDs and class names in SVG, HTML, and CSS (e.g., `icon-button`, `svg-logo`).

### CSS Custom Properties

Use **kebab-case** with double dashes for CSS custom properties (e.g., `--primary-color`).

### Attributes

Use **kebab-case** for HTML and SVG attribute names (e.g., `data-index`, `aria-label`).

### Files

- See [File Naming Conventions][FILE_NAMING_CONVENTIONS].

## Code Formatting and Style

The project adheres to the rules specified in the `.editorconfig`, `.prettierrc`, and `.markdownlint.json`
configuration files.

### Indentation and Spacing

Use **2 spaces** per indentation level throughout the project. Tabs are not permitted.
_(Enforced by EditorConfig)_

### Line Length

- **Code Files:**
  Limit lines to **88 characters**.
  _(Enforced by Prettier for supported files and yamllint pre-commit hook for `.yaml`/`.yml` files)_
- **Markdown/HTML/CSS/SVG:**
  Allow up to **120 characters** per line.
  _(Enforced by Prettier for HTML/CSS and by markdownlint pre-commit for Markdown)_

### Braces and Control Structures

- **Nested Elements:**
  Format nested elements with **2-space** indentation.
  _(Enforced by Prettier and EditorConfig)_
- **Tag Alignment:**
  Align opening and closing tags for clarity. For SVG files, the [jock.svg][jock.svg] VS Code extension is used.

### Comments and Documentation

- **General Guidance:**
  All comments should enhance clarity and avoid redundancy with well-named functions and variables.
  Ensure comments do not exceed the maximum line length.
- **Inline Comments:**
  Place concise inline comments on the same line or immediately above the code they describe.
- **Block Comments:**
  Use block comments for extended explanations.
- **File Header Comments:**
  Every file should begin with a header comment (except for files in `.json`, `.md`, and `LICENSE` files)
  that provides a short, third-person description of the file's purpose. For example:

  ```plaintext
  # .pre-commit-config.yaml: Sets up pre-commit hooks to automate code quality checks.
  ```

  If a file starts with a shebang (e.g., `#!/bin/bash`),
  place the header comment on the line immediately following the shebang.

### EditorConfig

- **Purpose:**
  The `.editorconfig` file ensures consistent coding styles across all editors by specifying:
  - **Indentation:** 2 spaces
  - **Line Endings:** Unix-style (`lf`)
  - **Charset:** UTF-8
  - **Max Line Length:** 88 for code, 120 for Markdown/HTML/CSS/SVG
    _(Note: `.editorconfig` provides these values for reference; enforcement is handled by other tools mentioned above.)_
  - **Final Newline:** Enforced
  - **Trailing Whitespace:** Trimmed (with specified exceptions)
- **Note:**
  Contributors should use an editor that supports EditorConfig to automatically apply these settings.

### Prettier

- **Purpose:**
  The `.prettierrc` file defines the project's code formatting rules,
  ensuring a consistent style across various file types by specifying:
  - **Semicolons:** Enabled
  - **Quote Style:** Single quotes preferred
  - **Trailing Commas:** Added where possible
  - **Tab Width:** 2 spaces (tabs are not used)
  - **End of Line:** Unix-style (`lf`)
  - **Print Width:** 88 characters for code files
    _(Note: Overrides are applied for CSS, HTML, and Markdown files with a print width of 120,
    while JSON files have no enforced limit)_
- **Note:**
  Prettier is integrated locally and runs as part of a pre-commit hook to automatically format code before commits.

### Linting and Formatting Tools

- **jock.svg:**
  This extension is used exclusively to format SVG files, as Prettier does not support SVG formatting.
  Configuring VS Code to associate SVG files with HTML for Prettier is not allowed.

- **Prettier:**
  _(See the [Prettier][PRETTIER] section above for detailed configuration.)_
  Prettier runs as a pre-commit hook and can also be executed via npm scripts—for example, use `npm run format:write`
  to check and apply formatting.

- **EditorConfig:**
  _(See the [EditorConfig][EDITORCONFIG] section above for detailed configuration.)_

- **Pre-commit Hooks:**
  The project leverages pre-commit hooks to enforce code quality through automated checks.
  Key tools integrated via pre-commit include:

  - **pre-commit-hooks:**
    Ensures proper AST parsing, fixes line endings and trailing whitespace, manages mixed line endings,
    detects private keys, validates YAML and JSON syntax, checks for merge conflicts, detects case conflicts,
    and verifies executable shebangs.
  - **markdownlint-cli and markdown-link-check:**
    Enforces the style guide rules for Markdown files and validates links.
  - **yamllint:**
    Enforces the style guide rules for YAML files.

## Documentation

### Inline Documentation

See [Comments and Documentation][COMMENTS-AND-DOCUMENTATION].

### External Documentation

- **Repository Documentation:**
  The root-level `README.md` provides an overview, installation instructions, usage examples, etc.
  Additional key documents such as `CONTRIBUTING.md`, `STYLEGUIDE.md`, `SECURITY.md`,
  and `LICENSE` are also maintained at the repository root.

### Markdown References

- **Reference-Style Links:**
  Use reference-style links for clarity. For example:

  ```markdown
  [info][link]

  [link]: https://example.com
  ```

- **Local References:**
  For links to repository-related documents (e.g., `CONTRIBUTING.md` or `CODE_OF_CONDUCT.md`) or internal sections,
  use **SCREAMING_SNAKE_CASE** for link identifiers and omit the file extension for documents.
  For example:

  ```markdown
  See our [Code of Conduct][CODE_OF_CONDUCT].

  [CODE_OF_CONDUCT]: CODE_OF_CONDUCT.md
  ```

  And for internal sections:

  ```markdown
  See [File Naming Conventions][FILE_NAMING_CONVENTIONS].

  [FILE_NAMING_CONVENTIONS]: #file-naming-conventions
  ```

  **Note:** Local references should always appear at the top and be sorted alphabetically. For example:

  ```markdown
  [FILE_NAMING_CONVENTIONS]: #file-naming-conventions
  [SECURITY]: SECURITY.md
  [external-link]: https://example.com
  ```

- **External Links:**
  For links that reference external resources, use **kebab-case** for link identifiers. For example:

  ```markdown
  [info][external-link]

  [external-link]: https://example.com
  ```

  **Note:** External references should be sorted alphabetically and always appear below local references. For example:

  ```markdown
  [SECURITY]: SECURITY.md
  [external-link]: https://example.com
  ```

### Documentation Tools and Best Practices

#### Tools

_(In addition to the tools described in [Linting and Formatting Tools][LINTING-AND-FORMATTING-TOOLS])_

- **cspell:**
  A spellchecker designed for code and Markdown files.
  It runs as a pre-commit hook and can also be executed via the npm script `npm run spell:check`.

#### Versioning Documentation

- Documentation versioning is not implemented yet but will be managed using MkDocs in alignment with project releases.

#### Consistency and Updates

- Update documentation alongside code changes.
- Contributors should update docs when introducing new features or modifying existing functionality.

#### Style and Tone

- Maintain a semi-formal tone appropriate for a tech-oriented audience.
- Use clear, precise language and consistent formatting throughout.

#### Contribution Guidelines

- Documentation contributions follow the same process as code changes—submit pull requests for review
  according to the contribution guidelines.

## Additional Best Practices

### Security and Privacy

- Avoid exposing sensitive information in logs or error messages.
- Regularly review dependencies for security vulnerabilities.

### Error Handling and Logging

- Implement robust error handling to manage unexpected issues gracefully.
- Use structured logging to capture context without exposing sensitive data.

### Code Organization and Maintenance

- Keep the codebase clean and modular to facilitate understanding and future extensions.
- Regularly review and refactor code to eliminate redundancy.
- Use design patterns where appropriate to improve clarity and reusability.

## Conclusion

### Continuous Improvement

This document is a living resource that should evolve with the project.
As new best practices emerge or project requirements change, please update the guide to keep it relevant and effective.

### Feedback and Updates

Your input is valuable. If you have suggestions for improvements, clarifications, or additional guidelines,
please reach out to the maintainers or submit an [issue][issues]. For contributing guidelines,
refer to [`CONTRIBUTING.md`][CONTRIBUTING]; for security concerns, see [`SECURITY.md`][SECURITY];
for discussions, consult the project's [discussion board][discussions]
or contact the project owner at [evgenii.shiliaev@jekwwer.com][evgenii.shiliaev@jekwwer.com].

---

This document is based on a template by [Evgenii Shiliaev][evgenii-shiliaev-github],
licensed under [CC BY 4.0][jekwwer-markdown-docs-kit-license]. All additional content is licensed under [LICENSE][LICENSE].

[COMMENTS-AND-DOCUMENTATION]: #comments-and-documentation
[CONTRIBUTING]: CONTRIBUTING.md
[EDITORCONFIG]: #editorconfig
[FILE_NAMING_CONVENTIONS]: #file-naming-conventions
[LICENSE]: LICENSE
[LINTING-AND-FORMATTING-TOOLS]: #linting-and-formatting-tools
[PRETTIER]: #prettier
[SCOPE]: #scope
[SECURITY]: SECURITY.md
[discussions]: https://github.com/Jekwwer/svg-workspace/discussions
[evgenii-shiliaev-github]: https://github.com/Jekwwer
[evgenii.shiliaev@jekwwer.com]: mailto:evgenii.shiliaev@jekwwer.com
[issues]: https://github.com/Jekwwer/svg-workspace/issues
[jekwwer-markdown-docs-kit-license]: https://github.com/Jekwwer/markdown-docs-kit/blob/main/LICENSE
[jock.svg]: https://marketplace.visualstudio.com/items?itemName=jock.svg
