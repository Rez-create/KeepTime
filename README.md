# KeepTime

A minimal, full-screen digital clock and focus session stopwatch that runs in the browser and installs as a Progressive Web App (PWA).

**Live at [trykeeptime.netlify.app](https://trykeeptime.netlify.app)**

KeepTime is designed to provide a distraction-free, highly readable clock and timer suitable for desktop monitors, secondary displays, work sessions, and video frame setups.

## Features

- **Responsive Display**: Seven-segment digital display that scales smoothly to fill any screen without shifting layout as digits change.
- **Multiple Clock Faces**: Switch between three distinct faces in settings:
  - Seven-segment digital display
  - Split-flap flip clock
  - Round analog dial
- **Time & Date Formatting**: Support for 12-hour and 24-hour formats, with an optional date display in five formats.
- **Keep Screen Awake**: Built-in screen wake lock keeps phone and computer screens awake without dimming, timing out, or locking.
- **Customization**: Eight curated color presets plus a full RGB color picker.
- **Display Controls**: In-window zoom adjustments and one-click fullscreen mode.
- **Stopwatch & Session Management**: Built-in stopwatch for focused work sessions with task tracking and session notes.
- **Persistent State**: Clock preferences and session history are saved locally in the browser.
- **Offline & PWA Support**: Installable as a standalone app with full offline capabilities via service worker caching.

## Stopwatch Sessions

Switch to stopwatch mode using the **Time / Stopwatch** toggle in the top-right control bar. The session controls include:

- **Start**: Optionally enter a task list for the session, then begin timing.
- **Controls**: Pause, resume (using button or <kbd>Space</kbd>), and stop the timer.
- **Task Management**: Open the task drawer during a session to mark items complete, add new tasks, or remove tasks.
- **Session Notes**: When stopping a session, record notes and review unfinished tasks.
- **Task Carry-Over**: Incomplete tasks can be carried forward as suggestions for subsequent sessions.
- **History & Search**: Review past sessions with durations, notes, and tasks. Filter history using the search bar, or clear logs when needed.

All session data is persisted locally in the browser's `localStorage` and never leaves your device.

## Running Locally

KeepTime is built with vanilla HTML, CSS, and JavaScript with zero build steps or external dependencies.

Serve the project root with any static HTTP server:

```sh
# Using Python 3
python -m http.server 8000
```

Then visit <http://localhost:8000> in your browser.

> **Note**: Service workers and PWA installation require a secure context (`https://` or `localhost`).

## Installation

Open [trykeeptime.netlify.app](https://trykeeptime.netlify.app) (or your local `localhost` instance):
1. In Chrome, Edge, or Brave: click **Install** in the address bar.
2. On mobile (iOS / Android): tap the browser menu and select **Add to Home Screen**.

The installed app launches in dedicated fullscreen mode.

## Project Structure

| File / Folder | Purpose |
| --- | --- |
| `index.html` | Application layout, clock elements, controls, drawers, and modal dialogs |
| `style.css` | Responsive styling, typography, theme variables, and layout scaling |
| `script.js` | Clock engine, face rendering, display settings, UI interactions, and PWA registration |
| `sessions.js` | Stopwatch logic, session persistence, task management, and local storage |
| `sw.js` | Service worker managing offline caching and resource pre-caching |
| `manifest.webmanifest` | Web app manifest with display metadata and icons |
| `icons/` | Application icons and maskable assets |
| `fonts/` | Seven-segment digital typeface |

## Credits

Uses the [DS-Digital](http://ds-font.hypermart.net) typeface by Dusit Supasawat (see [`fonts/DIGITAL.TXT`](fonts/DIGITAL.TXT) for font terms).

## License

Released under the [MIT License](LICENSE).
