# Repository Guidelines

## Project Structure & Module Organization
- Root contains a single static page: `sebastian-eusebio-bedmar-gade-profile.html` with HTML, `<style>`-scoped CSS, and a small inline `<script>` for scroll effects.
- Sections are grouped semantically (hero, experience timeline, services, skills, highlights, education, certificates, footer). Reuse existing class patterns (e.g., `*-card`, `timeline-item`, `skill-category`) to keep styling consistent.
- CSS variables in `:root` define the palette and spacing tokens; extend those instead of hard-coding new colors.

## Build, Test, and Development Commands
- Open the file directly for a quick check: `open sebastian-eusebio-bedmar-gade-profile.html`.
- Serve locally if you need hash routing or font caching parity: `python3 -m http.server 8000` then visit `http://localhost:8000/sebastian-eusebio-bedmar-gade-profile.html`.
- No build step or dependencies are required; keep it dependency-free unless there is a clear benefit.

## Coding Style & Naming Conventions
- Use 4-space indentation and keep HTML semantic (`<section>`, `<nav>`, `<article>`) with concise, kebab-case class names.
- Extend existing CSS utility patterns (cards, grids, accent colors) and update shared variables when changing the theme.
- Place any new JS at the bottom of the HTML, keep it framework-free, and prefer small, readable functions without global leaks.

## Testing Guidelines
- No automated test suite exists; rely on manual verification in modern browsers.
- Validate responsive behavior at mobile, tablet, and desktop widths; ensure grid cards wrap cleanly and text remains legible.
- Manually confirm the navbar scroll state, intersection-observer reveal animations, smooth anchor scrolling, and all in-page links (e.g., `#work`, `#skills`).
- Recheck external assets (Google Fonts) load correctly when served via `python3 -m http.server`.

## Commit & Pull Request Guidelines
- Write imperative, concise commit subjects (e.g., `Polish hero spacing`, `Refine skills grid spacing`); include brief bodies when context is non-obvious.
- PRs should state the scope, list key changes, and note manual tests performed. Include before/after screenshots for visual tweaks and link related issues when available.

## Security & Configuration Tips
- Keep third-party additions minimal; prefer inline assets or local copies over new remote dependencies.
- Avoid introducing inline event handlers that could complicate CSP hardening later; keep scripts consolidated in the existing `<script>` block.
