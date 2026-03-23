# Repository Custom Instructions for GitHub Copilot

<!-- Reference: https://docs.github.com/en/copilot/how-tos/configure-custom-instructions/add-repository-instructions -->

## About This Repository

This is a GitHub profile README repository for [Karthik-R-1703](https://github.com/Karthik-R-1703). The `README.md` in the root is rendered as the public GitHub profile page. The `index.html` is a standalone portfolio page hosted via GitHub Pages.

## Repository Structure

- `README.md` — GitHub profile page (HTML + Markdown mix).
- `index.html` — Portfolio page hosted via GitHub Pages (brutalist/monospace design inspired by rentahuman.ai).
- `style.css` — External stylesheet for `index.html`. Uses CSS custom properties for dark/light theme support.
- `_config.yml` — Jekyll configuration for `jekyll-sitemap` plugin (auto-generates `sitemap.xml`).
- `Gemfile` — Ruby gem dependencies for local Jekyll testing (`github-pages` gem).
- `404.html` — Custom 404 error page matching the brutalist design.
- `robots.txt` — Search engine crawler directives pointing to the auto-generated sitemap.
- `manifest.json` — Web app manifest for PWA-like behavior and mobile "Add to Home Screen".
- `og-image.svg` — Open Graph social preview image (1200×630, black bg, monospace text).
- `Resume.md` — Local reference only; excluded from Git via `.gitignore`.
- `.github/copilot-instructions.md` — This file; Copilot custom instructions.
- `.gitignore` — Excludes local-only files (`Resume.md`, `*.docx`, editor/OS artifacts, Jekyll build artifacts).

## Guidelines

- The README uses a mix of HTML and Markdown for layout. Preserve the HTML structure (`<h1>`, `<h3>`, `<p>`, `<a>`, `<img>` tags with alignment attributes) — do not convert them to plain Markdown.
- All icon/tool images must include explicit `width` and `height` attributes (40x40 for tools, height="30" width="40" for social icons) to prevent oversized rendering.
- Social link icons come from `rahuldkjain/github-profile-readme-generator`. Language/tool icons come from `devicons/devicon` and `vectorlogo.zone`. AI tool icons use `cdn.simpleicons.org` with brand hex colors (e.g., `/githubcopilot/8957E5`).
- Keep the profile visually clean and consistent. Avoid adding raw Markdown image syntax (`![alt](url)`) for icons — use HTML `<img>` tags with size attributes instead.
- When adding new projects, link them to the actual GitHub repository and include a brief description with technologies used.
- Do not add placeholder or template content (e.g., "Project Name" or "Add your projects here").
- The `index.html` portfolio page uses a brutalist monospace design (pure black background, numbered sections, ticker bar, emoji highlight cards). CSS is in `style.css` using custom properties (`--bg`, `--text`, etc.) for dark/light theme support. Keep content in sync with the README when changes are made.
- The `Resume.md` file is for local reference only and is not pushed to Git.

## GitHub Pages

- The site is hosted via GitHub Pages as a static site. `index.html` and `404.html` are plain HTML — no Jekyll front matter or Liquid tags.
- SEO meta tags (title, description, OG, Twitter, canonical) are hardcoded in the `<head>` of `index.html`. Update them directly when changing site metadata.
- Asset links (`style.css`, `manifest.json`) use plain relative paths so the page works when opened locally as a file or served via GitHub Pages.
- The page can be tested locally by simply opening `index.html` in a browser — no build step required.

## Design Patterns (index.html + style.css)

- **Sections** are numbered (`01 / about`, `02 / experience`, etc.) with `.section-label` elements. Currently 9 sections: about, experience, education, projects, process, tools, stats, learning, connect.
- **Experience timeline**: `.timeline` container with `.timeline-item` children, `.timeline-dot` markers, and `.exp-card` content. Vertical line via `::before` pseudo-element.
- **Skills**: Categorized in `.skills-category` divs with `.skills-category-label` and `.skills-grid`. Each icon is a `.skill-icon` `<a>` with `data-tooltip` (shown via CSS `::after`). `aria-label` is applied dynamically via JS from `data-tooltip`.
- **Learning cards**: `.learning-grid` with `.learning-card` items (emoji + heading + description).
- **Theme toggle**: `[data-theme="light"]` CSS custom properties + `localStorage` persistence. Toggle button is `#themeToggle`.
- **Animations**: `fadeUp` for hero entrance, `sectionReveal` for nav-click transitions, `sectionPulse` for heading highlight, `scroll` for ticker. All respect `prefers-reduced-motion`.
- **Font**: Fira Code via Google Fonts, preloaded with `<link rel="preload" as="style">`.
- **PWA**: `manifest.json` + `<meta name="theme-color">` with media queries for dark/light.
