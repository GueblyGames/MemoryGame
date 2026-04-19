<div align="center">

<img src="https://games.guebly.com.br/gueblygames.png" alt="Guebly Games" width="240"/>

# Contributing to Memory Game

Thank you for taking the time to contribute! This game is part of the [Guebly Games](https://games.guebly.com.br) web games collection.

</div>

---

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [How to Report a Bug](#how-to-report-a-bug)
- [How to Suggest a Feature](#how-to-suggest-a-feature)
- [Development Setup](#development-setup)
- [Branching & Commit Convention](#branching--commit-convention)
- [Pull Request Process](#pull-request-process)
- [Code Style Guide](#code-style-guide)
- [Suggestions for Contribution](#suggestions-for-contribution)

---

## Code of Conduct

Be respectful, constructive, and welcoming. We want this to be a fun and collaborative project. Any form of harassment, discrimination, or toxic behavior will not be tolerated.

---

## How to Report a Bug

1. Search the [Issues](https://github.com/GueblyGames/JogoDaMemoria/issues) tab to make sure it hasn't been reported yet.
2. Open a new issue with the label `bug`.
3. Include the following:
   - **Description:** What happened vs. what you expected
   - **Steps to reproduce:** Numbered steps to trigger the bug
   - **Browser & OS:** e.g. Chrome 124 on Windows 11
   - **Screenshot or screen recording** (if applicable)

---

## How to Suggest a Feature

1. Search the [Issues](https://github.com/GueblyGames/JogoDaMemoria/issues) tab to avoid duplicates.
2. Open a new issue with the label `enhancement`.
3. Describe:
   - The feature you'd like to see
   - Why it would improve the game
   - Any UI/UX ideas or references you have in mind

---

## Development Setup

This project has **no build step and no dependencies**. All you need is a browser.

```bash
# 1. Fork the repository on GitHub, then clone your fork
git clone https://github.com/YOUR_USERNAME/JogoDaMemoria.git

# 2. Open the project folder
cd JogoDaMemoria

# 3. Open index.html in your browser
#    (We recommend using the Live Server extension for VS Code to avoid CORS issues)
open index.html       # macOS
start index.html      # Windows
xdg-open index.html   # Linux
```

**Recommended tools:**
- [VS Code](https://code.visualstudio.com/) with the [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer) extension
- Any modern browser (Chrome, Firefox, Edge, Safari)

---

## Branching & Commit Convention

**Branch naming:**

| Type | Pattern | Example |
|---|---|---|
| New feature | `feat/description` | `feat/sound-effects` |
| Bug fix | `fix/description` | `fix/card-flip-double-click` |
| Documentation | `docs/description` | `docs/update-readme` |
| Style / UI | `style/description` | `style/mobile-layout` |
| Refactor | `refactor/description` | `refactor/game-state` |

**Commit messages** follow [Conventional Commits](https://www.conventionalcommits.org/):

```
feat: add sound effects on card match
fix: prevent double-clicking the same card
docs: update contributing guide
style: improve mobile card sizing
refactor: extract shuffle into separate function
```

---

## Pull Request Process

1. Fork the repository and create your branch from `main`.
2. Make your changes following the [Code Style Guide](#code-style-guide).
3. Test your changes manually in at least one browser.
4. Make sure the game still works end-to-end (login → game → win screen).
5. Open a Pull Request against the `main` branch with:
   - A clear title describing what changed
   - A description of **what** you changed and **why**
   - Screenshots or a GIF if the change is visual

> Pull Requests that break the game flow or introduce external dependencies will not be merged.

---

## Code Style Guide

This project uses **vanilla HTML, CSS, and JavaScript** with no linter configured. Please follow these conventions to keep the codebase consistent:

**HTML**
- Use semantic elements (`<header>`, `<main>`, `<section>`, etc.)
- Always include `alt` attributes on images
- Keep indentation at 2 spaces

**CSS**
- Keep selector specificity low — prefer class selectors
- Group related properties (box model, typography, color, animation)
- Add comments above major sections
- Mobile-first or breakpoint-based responsive styles go at the bottom

**JavaScript**
- Use `let`/`const`, no `var`
- Keep game logic in `game.js` and DOM manipulation in `script.js`
- Descriptive variable and function names in English or Portuguese (be consistent within a file)
- Avoid inline event handlers in HTML — use `addEventListener` when adding new features
- No external libraries or npm packages

---

## Suggestions for Contribution

Looking for ideas? Here are some open directions:

- Add **Neptune** and other missing planets to complete the solar system
- Add **difficulty levels** (easy: 3×4, medium: 4×5, hard: 5×6)
- Add **background music** and **sound effects** on card flip, match, and win
- Add a **local high score** leaderboard using `localStorage`
- Add **card themes** (animals, countries, flags, etc.)
- Improve **accessibility**: keyboard navigation, ARIA labels, screen reader support
- Add a **dark/light mode toggle**
- Add **animations** to the win screen (confetti, stars, etc.)

---

<div align="center">

Made with ❤️ by [Guebly Games](https://games.guebly.com.br)

<img src="https://games.guebly.com.br/games.png" alt="Guebly Games" width="140"/>

</div>
