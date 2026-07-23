# Countdown

A sleek, full-screen countdown timer built as a single HTML file — no dependencies, no build step. Click the time, press **Space**, and watch the countdown.

![Screenshot](https://img.shields.io/badge/status-ready-brightgreen) ![License](https://img.shields.io/badge/license-MIT-blue)

---

## Features

- 🎯 **Click-to-edit** – Click any time field (hours, minutes, seconds) and type a new value.
- ⏱ **Wall-clock accuracy** – Uses `Date.now()` internally so the countdown stays accurate even when the browser tab is backgrounded.
- ⌨️ **Full keyboard control** – Space to start/pause, R to reset, F for fullscreen, arrow keys to nudge values, Tab/arrows to move between fields.
- 🖱 **Auto‑hiding cursor** – Mouse cursor fades after 5 seconds of inactivity during a running countdown (ideal for projection or kiosk use).
- 📱 **Responsive** – Works on any screen size, with special handling for landscape phones and high‑contrast / reduced‑motion preferences.
- 💾 **Persistent duration** – Your configured time is saved to `localStorage` and restored on reload.
- 🎨 **Dark, minimal UI** – Large tabular numerals, subtle instructions, and a bold red "Time's Up" screen.

---

## Usage

1. Open `index.html` in any modern browser.
2. **Edit** – Click the minutes or seconds field (or press ↑ / ↓) to set a time.
3. **Start** – Press **Space** (or click the timer area and press Space).
4. **Pause / Resume** – Press **Space** again.
5. **Reset** – Press **R** to return to the configured duration.
6. **Fullscreen** – Press **F** for a distraction‑free view.

> The timer also works when editing: type a value and press **Space** to commit and start counting immediately.

---

## Keyboard Shortcuts

| Key           | Action                         |
|---------------|--------------------------------|
| `Space`       | Start / pause / resume         |
| `R`           | Reset to configured duration   |
| `F`           | Toggle fullscreen              |
| `↑` / `↓`     | Increase / decrease time       |
| `Tab` / `→`   | Move to next field             |
| `Shift+Tab` / `←` | Move to previous field      |
| `Enter`       | Commit editing                 |
| `Escape`      | Cancel editing                 |

---

## File Structure

```
index.html   ← the entire application (HTML, CSS, and JavaScript in one file)
README.md    ← this file
```

---

## Customisation

Everything is in one file. Key variables you may want to tweak:

- **`DEFAULT_SECONDS`** (line 325) – Initial countdown value (default: `3300` = 55 minutes).
- **`--color-*`** custom properties in the `<style>` block – Background, text, and "finished" colours.
- **Font** – The timer uses [Inter](https://fonts.google.com/specimen/Inter) (loaded from Google Fonts) with a fallback stack.

---

## Technical Details

- **Zero dependencies.** Pure HTML5, CSS3, and vanilla ES5/ES6.
- **requestAnimationFrame** drives the display at ~30 fps for smooth updates.
- **`Math.ceil`** is used for the remaining‑seconds calculation so that a freshly started 1‑second timer shows `1` for one full second (matching the behaviour of BigTimer.net).
- **localStorage** persists the configured duration under the key `countdown_configured_seconds`.
- The entire app respects `prefers-reduced-motion` and `prefers-contrast` media queries.

---

## Browser Support

Works in all modern browsers: Chrome, Firefox, Safari, Edge. Internet Explorer is **not** supported.

---

## License

MIT – do whatever you like with it.