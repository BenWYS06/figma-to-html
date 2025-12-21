<!-- Copilot / AI agent instructions for this repository -->

# Copilot instructions

This is a small static site (single HTML page) with a simple asset layout. Keep suggestions focused, minimal, and consistent with the existing CSS-first structure.

- **Big picture**: A single-page site centered on `index.html` that imports two CSS files (`assets/css/reset.css`, `assets/css/style.css`) and Google fonts. No JS build system or package manager is present.
- **Key files**: [index.html](index.html), [assets/css/reset.css](assets/css/reset.css), [assets/css/style.css](assets/css/style.css), `assets/img/` (images).

- **Layout / conventions**:

  - Typography uses `html { font-size: 62.5% }` and `rem` units across `assets/css/style.css` (see `html` / `body` rules). Preserve that base when adding new styles.
  - Central container: `.main-content` centers pages with a fixed design width of `1170px` and `max-width: calc(100% - 48px)`; new sections should reuse that container.
  - Navigation uses `.nav` and `.nav li.active a::after` pseudo-element to highlight active items. The pseudo-element is defined as `position: absolute` — ensure the positioned parent exists when editing or adding similar pseudo-elements.
  - Class naming is flat (no strict BEM); prefer short, semantic class names already present (e.g., `.header`, `.nav`, `.logo`, `.action`, `.main-content`).

- **Assets & external integrations**:

  - Fonts are loaded from Google Fonts via `link` in `index.html`; keep or update font families there (no font build pipeline).
  - Images live in `assets/img/` and are referenced with relative paths (e.g., `./assets/img/Logo.svg`).

- **Editing guidance for AI agents**:

  - Make minimal, atomic changes. Prefer editing or adding CSS in `assets/css/style.css` and avoid creating new build files or tooling.
  - Follow existing units and spacing: use `rem` for font sizes and keep the `1170px` design width pattern for centered content blocks.
  - If adding interactive behavior, note there is currently no JS folder; add `assets/js/` only when proposals include a simple script file and an updated `index.html` `<script>` include.
  - When modifying navigation highlight use a positioned ancestor (e.g., add `position: relative` to the anchor or `li`) so `::after { position: absolute }` behaves correctly.

- **Testing / preview**:

  - There is no build step — preview by opening [index.html](index.html) directly in a browser.

- **What not to change without asking**:
  - Do not change `reset.css` unless the change is narrowly scoped and explained; it's the project's global reset.
  - Avoid changing Google Fonts links unless adjusting typography with explicit reasons.

If anything above is unclear or you'd like the instructions expanded (examples for adding a new section, or a small `assets/js/` pattern), tell me which area to expand and I'll update this file.
