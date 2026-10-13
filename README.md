# git-infographic

**git101** is a beginner-friendly guide to Git, presented as a static infographic site. It is plain HTML and CSS: no frameworks, no JavaScript, no build step.

> **AI disclosure:** the inline SVG illustrations on the Commands page (`commands.html`) were **created by AI**. See [AI disclosure](#ai-disclosure) for details.

## Pages

| Page | File | What it covers |
| --- | --- | --- |
| Home | `index.html` | Hero section and four feature cards: track changes, branches, collaboration, undo |
| Git vs GitHub | `git-vs-github.html` | Side-by-side comparison of Git and GitHub, summary, and a note on Git's creator |
| Commands | `commands.html` | Visual flow from working directory to GitHub, plus 12 essential commands grouped by task |

The commands page groups its 12 commands into four sets of three: **Get started**, **Save your work**, **Branch and merge**, and **Share and undo**.

## Features

- Shared navigation with an active-page highlight
- Two-tone orange and black theme (orange for Git, black for GitHub), defined as CSS custom properties
- Automatic light and dark mode through `prefers-color-scheme`
- Responsive layout with breakpoints at 850px, 600px, and 380px
- Keyboard focus styles and decorative icons hidden from screen readers on the commands page

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
git clone https://github.com/Kleyen/git-infographic.git
cd git-infographic
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Linting

Dev dependencies ([html-validate](https://html-validate.org/) and [stylelint](https://stylelint.io/)) are used for checks only. The site itself has no runtime dependencies.

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
│   └── style.css        # theme variables, nav, layout, page sections, dark mode
├── assets/              # logo and feature icons (from SVG Repo)
├── .htmlvalidate.json   # html-validate rules
├── .stylelintrc.json    # stylelint config
├── package.json         # lint tooling only (dev dependencies)
└── .github/workflows/
    └── ci.yml           # lint + link checks
```

## Built with

- HTML5
- CSS (custom properties, grid and flexbox, no framework)

## AI disclosure

The inline SVG illustrations in `commands.html` were **created by AI**. This covers:

- the workflow stage icons in the "From your files to GitHub" section (working directory, staging area, local repository)
- the per-command illustrations in the quick-reference cards

The icons in `assets/` and the four feature icons on `index.html` are not AI-made; see [Credits](#credits).

## Roadmap

- [x] Shared navigation with an active-page highlight
- [x] Home page
- [x] Lint and CI setup
- [x] Git vs GitHub page content
- [x] Commands cheat sheet

## Credits

- The icon files in `assets/` are from [SVG Repo](https://www.svgrepo.com), and the four feature icons on `index.html` are inlined copies of them. Check each icon's page there for its license before reusing it.
- Git and GitHub are trademarks of their respective owners. This project is an educational guide and is not affiliated with either.
