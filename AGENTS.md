# Repository Guidelines

## Project Structure & Module Organization

This repository is a single-page, static résumé site. Keep the document content
in `index.html`. Styles live in `styles/base.css` (variables and shared layout),
`styles/resume.css` (résumé components), and `styles/print.css` (print rules).
The HTML is arranged as header and résumé sections (summary, skills, experience,
education, and projects); preserve that semantic structure when editing. Styles
use CSS custom properties in `:root` and reusable selectors such as `.job-entry`.
There are currently no generated assets or test files.

## Build, Test, and Development Commands

No dependency installation, build step, or test runner is required. Open the
page directly in a browser during development:

```bash
xdg-open index.html
```

For a local HTTP preview when browser file access is inconvenient, run:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`. Use the browser's print preview to validate
the résumé's primary output; it should remain readable and paginate as intended.

## Coding Style & Naming Conventions

Use two-space indentation in HTML and four-space declaration indentation in
CSS; `.editorconfig` provides editor defaults. Prefer semantic HTML (`header`,
`section`, headings, lists) over generic containers. Use lowercase, hyphenated
class names such as `.contact-info`, `.skills-grid`, and `.page-break`. Reuse
the color variables in `:root` rather than introducing repeated literal colors.
Keep visible résumé text concise, factual, and free of placeholder links or
empty list items.

## Testing Guidelines

There is no automated test framework or coverage target. Before submitting,
open the page at desktop and narrow viewport widths, check that links work, and
inspect print preview. Confirm that `@media print` hides non-print controls,
page breaks occur deliberately, and headings or bullet entries are not split
awkwardly across pages.

## Commit & Pull Request Guidelines

Recent history favors short, focused subjects, commonly using prefixes such as
`fix: edit html`. Follow that pattern: write imperative, scoped messages such
as `fix: align education dates` or `style: tighten print spacing`. Keep each
commit limited to one résumé or layout concern. Pull requests should summarize
the content or visual change, link any relevant issue, and include before/after
screenshots or print-preview images for layout changes. State how browser and
print validation were performed.
