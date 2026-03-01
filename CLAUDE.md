# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

Cyberpunk-themed Snake game built as a single self-contained HTML file.

## How to Run

- Open `snake.html` directly in a browser; no build step or dependencies needed

## Architecture

- **Single file**: All HTML, CSS, and JavaScript live in `snake.html`
- **Canvas-based rendering**: Uses HTML5 `<canvas>` for the game board (600x600, 30x30 grid)
- **Game loop**: `setInterval`-based tick with configurable speed (35ms–120ms)
- **Particle system**: Lightweight array-based particles for food collection and death effects

## Key Design Decisions

- **Cyberpunk aesthetic**: Neon cyan (`#00ffff`) and magenta (`#ff00ff`) color scheme, Orbitron + Share Tech Mono fonts (loaded via Google Fonts), scanline overlay, glowing box-shadows
- **No external dependencies**: Fonts are the only external resource; game runs fully offline once cached
- **Local storage**: High score persists via `localStorage` key `cyberSnakeHighScore`
- **Mobile support**: Touch controls auto-appear on touch devices (`pointer: coarse` media query)

## Game Controls

| Input | Action |
|-------|--------|
| WASD / Arrow keys | Move snake |
| Enter | Start / Restart |
| Escape | Pause / Resume |
| Touch d-pad | Move (mobile) |

## Modification Tips

- Grid size and tile count are set via `GRID_SIZE` and `TILE_COUNT` constants at the top of the script
- Speed presets are defined in the HTML speed buttons (`data-speed` attribute, value in ms)
- Color palette is concentrated in the CSS custom properties area and the `draw()` function
- To add wall-wrap mode, modify the wall collision check in `update()` to wrap coordinates instead of calling `gameOver()`
