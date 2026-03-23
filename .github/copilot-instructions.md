# Repository Custom Instructions for GitHub Copilot

<!-- Reference: https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions -->

## About This Repository

This is a GitHub profile README repository for [Karthik-R-1703](https://github.com/Karthik-R-1703). The `README.md` in the root is rendered as the public GitHub profile page. The `index.html` is a standalone portfolio page hosted via GitHub Pages.

## Repository Structure

- `README.md` — GitHub profile page (HTML + Markdown mix).
- `index.html` — Portfolio page hosted via GitHub Pages (brutalist/monospace design inspired by rentahuman.ai).
- `style.css` — External stylesheet for `index.html`. Uses CSS custom properties for dark/light theme support.
- `og-image.svg` — Open Graph social preview image (1200×630, black bg, monospace text).
- `Resume.md` — Local reference only; excluded from Git via `.gitignore`.
- `.github/copilot-instructions.md` — This file; Copilot custom instructions.
- `.gitignore` — Excludes local-only files (`Resume.md`, `*.docx`, `TODO.md`, editor/OS artifacts).

## Guidelines

- The README uses a mix of HTML and Markdown for layout. Preserve the HTML structure (`<h1>`, `<h3>`, `<p>`, `<a>`, `<img>` tags with alignment attributes) — do not convert them to plain Markdown.
- All icon/tool images must include explicit `width` and `height` attributes (40x40 for tools, height="30" width="40" for social icons) to prevent oversized rendering.
- Social link icons come from `rahuldkjain/github-profile-readme-generator`. Language/tool icons come from `devicons/devicon` and `vectorlogo.zone`.
- Keep the profile visually clean and consistent. Avoid adding raw Markdown image syntax (`![alt](url)`) for icons — use HTML `<img>` tags with size attributes instead.
- When adding new projects, link them to the actual GitHub repository and include a brief description with technologies used.
- Do not add placeholder or template content (e.g., "Project Name" or "Add your projects here").
- The `index.html` portfolio page uses a brutalist monospace design (pure black background, numbered sections, ticker bar, emoji highlight cards). CSS is in `style.css` using custom properties (`--bg`, `--text`, etc.) for dark/light theme support. Keep content in sync with the README when changes are made.
- The `Resume.md` file is for local reference only and is not pushed to Git.
