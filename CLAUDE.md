# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project

This is a single-file, vanilla HTML/CSS/JavaScript web app — no build step, no dependencies, no package manager.

**To run:** open `tictactoe.html` directly in a browser.

## Architecture

All game logic lives in `tictactoe.html`:

- **UI** — a 3×3 CSS Grid board; cells get `.x`/`.o`/`.taken`/`.win` classes for styling.
- **Game state** — `cells` (9-element array), `current` (active player), `gameOver`, `mode` (`'2p'` or `'1p'`), `score`.
- **AI** — minimax (`minimax()`) used for Hard difficulty; `bestMove()` picks the optimal cell for the CPU (always plays as `'O'`). Easy uses random moves; Medium mixes both.
- **Flow** — `handleClick` → `placeMove` → win/draw check → if CPU's turn, `setTimeout(cpuMove, 400)`.
