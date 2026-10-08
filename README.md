# git-infographic

**git101** — a beginner-friendly guide to Git, presented as a simple static infographic site. No frameworks, no build step.

> **Status:** work in progress. Shared navigation, styling, and the home page hero are in place; page content is still to come.

## Pages

| Page | File | Status |
| --- | --- | --- |
| Home | `index.html` | Completed |
| Git vs GitHub | `git-vs-github.html` | Completed |
| Commands | `commands.html` | Completed |

## Run locally

The site is plain HTML/CSS/JS — open `index.html` in a browser, or serve the folder:

```bash
git clone https://github.com/Kleyen/git-infographic.git
cd git-infographic
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Linting

Dev dependencies ([html-validate](https://html-validate.org/), [stylelint](https://stylelint.io/)) are used for CI only — the site itself has no runtime dependencies.

```bash
npm ci
npm run lint        # all checks
npm run lint:html   # validate HTML
npm run lint:css    # lint CSS
```

CI (`.github/workflows/ci.yml`) runs the lint suite and an offline [lychee](https://github.com/lycheeverse/lychee) link check on every push and pull request.

## Project structure

```text
git-infographic/
├── index.html
├── git-vs-github.html
├── commands.html
├── css/
│   └── style.css        # theme colors as CSS variables, nav, hero, layout
├── scripts/
│   └── script.js        # placeholder for dark mode
├── assets/              # logo icons
├── package.json         # lint tooling only (dev dependencies)
└── .github/workflows/
    └── ci.yml           # lint + link checks
```

## Built with

- HTML5
- CSS (custom properties, no framework)
- Vanilla JavaScript (placeholder only)

## Roadmap

- [x] Shared navigation with an active-page highlight
- [x] Home page
- [x] Lint + CI setup
- [x] Git vs GitHub page content
- [x] Commands cheat sheet

## Credits

Icons are from [SVG Repo](https://www.svgrepo.com). Check each icon's page there for its license before reusing it.
