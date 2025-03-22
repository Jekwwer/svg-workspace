# SVG Workspace

![GitHub Release](https://img.shields.io/github/v/release/Jekwwer/svg-workspace?logo=github&link=https%3A%2F%2Fgithub.com%2FJekwwer%2Fsvg-workspace%2Freleases%2Flatest)
![GitHub Release Date](https://img.shields.io/github/release-date/Jekwwer/svg-workspace?link=https%3A%2F%2Fgithub.com%2FJekwwer%2Fsvg-workspace%2Freleases%2Flatest)
![GitHub commits since latest release](https://img.shields.io/github/commits-since/Jekwwer/svg-workspace/latest?link=https%3A%2F%2Fgithub.com%2FJekwwer%2Fsvg-workspace%2Freleases%2Flatest)
![Libraries.io dependency status for GitHub repo](https://img.shields.io/librariesio/github/Jekwwer/svg-workspace?logo=librariesdotio&logoColor=%23FFFFFF)
![Issues](https://img.shields.io/github/issues/Jekwwer/svg-workspace?logo=github&link=https%3A%2F%2Fgithub.com%2FJekwwer%2Fsvg-workspace%2Fissues)
![Maintained](https://img.shields.io/maintenance/yes/2025)
![GitHub License](https://img.shields.io/github/license/Jekwwer/svg-workspace?link=https%3A%2F%2Fgithub.com%2FJekwwer%2Fsvg-workspace%2Fblob%2Fmain%2FLICENSE)

## Project Overview 🚀

A minimal SVG development template that provides a ready-to-use devcontainer, custom VS Code settings,
consistent formatting, spell checking, and essential repository files.

## Features ✨

- **Devcontainer:**
  A Node-based environment with Python 3.12 support, custom VS Code settings, and the [**jock.svg**][jock.svg] extension
  as the primary SVG formatter.
- **Formatting:**
  Ensures a consistent code style using **Prettier**, **EditorConfig**, **markdownlint**, and [**jock.svg**][jock.svg]
  for SVG files.
- **Spell Checking:**
  Automatically highlights spelling errors.
- **Pre-commit Hooks:**
  Automates quality checks before each commit using pre-commit hooks.
- **Release Automation:**
  Manages releases automatically.
- **Dependency Updates Automation:**
  Automates dependency updates via Dependabot.

## Installation 📦

This setup is designed for **GitHub Codespaces**.
Running locally has **not been tested** and may require additional configuration.

[![Open in GitHub Codespaces](https://github.com/codespaces/badge.svg)][open-in-codespaces]

## Usage 🛠️

### Formatting

Most formatting tasks are automated and enforced in this repository using various tools.
Feel free to adjust these settings for your project.
The repository configurations are described in the [`STYLEGUIDE.md`][STYLEGUIDE].

- **SVG Files:**
  The [jock.svg][jock.svg] VS Code extension is used exclusively for formatting SVG files.
  It automatically formats SVGs in the editor when the following settings are enabled
  (already configured in the devcontainer):

  - `editor.formatOnPaste`: true
  - `editor.formatOnSave`: true
  - `files.autoSave`: onFocusChange

- **Non-SVG Files:**
  Use **Prettier** to format all other files supported by Prettier.

  To apply formatting to your code, run:

  ```bash
  npm run format:write
  ```

  For a formatting check without modifying files, run:

  ```bash
  npm run format:check
  ```

### Spell Checking

To run spell checking, execute:

```bash
npm run spell:check
```

Spell checking is also configured as a pre-commit hook. Adjust the `cspell.json` configuration file if needed.

## Contributing 👥

Contributions are welcome! Please read the [Contributing Guidelines][CONTRIBUTING] and check the [Issues][issues] page.

## License 🛡️

This project is licensed under the [MIT License][LICENSE].

## Contact 📬

For questions, reach out via [evgenii.shiliaev@jekwwer.com][evgenii.shiliaev@jekwwer.com] or open an [issue][issues].

---

This document is based on a template by [Evgenii Shiliaev][evgenii-shiliaev-github],
licensed under [CC BY 4.0][jekwwer-markdown-docs-kit-license]. All additional content is licensed under [LICENSE][LICENSE].

[CONTRIBUTING]: CONTRIBUTING.md
[LICENSE]: LICENSE
[STYLEGUIDE]: STYLEGUIDE.md
[evgenii-shiliaev-github]: https://github.com/Jekwwer
[evgenii.shiliaev@jekwwer.com]: mailto:evgenii.shiliaev@jekwwer.com
[issues]: https://github.com/Jekwwer/svg-workspace/issues
[jock.svg]: https://marketplace.visualstudio.com/items?itemName=jock.svg
[jekwwer-markdown-docs-kit-license]: https://github.com/Jekwwer/markdown-docs-kit/blob/main/LICENSE
[open-in-codespaces]: https://codespaces.new/Jekwwer/svg-workspace
