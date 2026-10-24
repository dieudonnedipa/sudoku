# Sudoku

A personal, ad-free Sudoku game that runs in the browser and installs on your phone as a PWA (Progressive Web App). No ads, no tracking, no account. Everything is stored locally on your device and it works offline.

Live: https://dieudonnedipa.github.io/sudoku/

## Features

- 4 difficulty levels: Easy, Medium, Hard, Expert
- Every puzzle has exactly one solution
- Notes (pencil marks), with auto-removal of notes when a digit is placed
- Notes are blocked if the number is already placed in the same row, column or box
- Quick mode: pick a number once, then tap as many cells as you want
- Highlighting of the row, column, box, same digits, and same digits inside notes
- Number pad shows how many of each digit are left, and turns gray in notes mode
- Undo, Erase, Hint
- 3 mistakes allowed, wrong digits shown in red
- Auto-save and resume
- Stats per difficulty: played, won, best time, streak
- Settings: theme (auto, light, dark), timer, vibration, highlighting
- Works offline

## Files

| File | Purpose |
| --- | --- |
| `index.html` | The whole app (HTML, CSS, JavaScript) |
| `manifest.json` | PWA manifest (name, icons, colors) |
| `sw.js` | Service worker (offline support, auto-updates) |
| `icon-192.png`, `icon-512.png` | App icons |

## How to play

- Tap a cell, then tap a number to place it.
- Turn on **Notes** to add pencil marks instead of real digits.
- Turn on **Quick**, tap a number, then tap cells to fill them one after another. With Notes on, it toggles notes; with Notes off, it places digits.
- Tap the active number again to deselect it.
- **Hint** fills the selected cell, or the first empty or wrong one.
- On a computer: keys 1-9 place numbers, Backspace erases, `N` toggles notes, arrows move the selection.

## Deploy on GitHub Pages

1. Create a public repository (for example `sudoku`).
2. Put all the files at the root of the repository, not inside a subfolder.
3. Go to **Settings → Pages**, choose branch `main` and `/ (root)`, then **Save**.
4. After 1 to 2 minutes, the app is live at `https://YOUR-USERNAME.github.io/sudoku/`.

With git:

```bash
git add .
git commit -m "update"
git push
```

## Install on Android

1. Open the link in **Chrome**.
2. Tap ⋮ → **Add to Home screen** (or **Install app**).
3. Launch it from the home screen. It opens fullscreen.

## Updating

The service worker loads the latest files whenever you are online and falls back to the cache when you are offline. After pushing changes, close and reopen the app. If an old version still shows, clear the site data in Chrome (Site settings → `dieudonnedipa.github.io` → Clear & reset). This also erases the saved game and stats.

## Data

Everything is saved in the browser's `localStorage` on your device:

- `sdk-game`: current game
- `sdk-stats`: statistics
- `sdk-set`: settings

Nothing is sent anywhere.
