# Ludi's 60m

A minimal Pomodoro-style focus timer, installable as a PWA. It cycles through focus and break sessions, tracks daily/weekly stats locally on your device, and remembers your theme and timer preferences between visits.

**[Live demo →](https://francescogemolo.github.io/pomodoro-ts/)**

## Features

- Focus → short break cycle, with a long break every 4th session
- Session and streak tracking, persisted in `localStorage`
- 7-day focus chart and all-time stats
- Configurable focus / short break / long break durations
- Light and dark theme, respecting the system preference on first load
- Installable PWA with offline support (service worker precaching via `vite-plugin-pwa`)
- Fully responsive layout for mobile, tablet and desktop

## Tech stack

- [React 19](https://react.dev/) + [TypeScript](https://www.typescriptlang.org/)
- [Vite](https://vite.dev/) for tooling and bundling
- [vite-plugin-pwa](https://vite-pwa-org.netlify.app/) for the service worker and manifest
- [lottie-react](https://github.com/Gamote/lottie-react) for the cat animation
- [oxlint](https://oxc.rs/) for linting

## Getting started

```bash
npm install
npm run dev
```

The app runs at `http://localhost:5173` by default.

### Scripts

| Command            | Description                              |
| ------------------ | ----------------------------------------- |
| `npm run dev`       | Start the dev server                     |
| `npm run build`      | Type-check and build for production      |
| `npm run preview`     | Preview the production build locally     |
| `npm run lint`       | Run oxlint                               |
| `npm run typecheck`    | Run the TypeScript compiler in check mode |
| `npm run deploy`      | Build and publish to GitHub Pages        |

## Project structure

```
src/
├── assets/
│   ├── animations/     # Lottie animation data
│   └── fonts/          # Self-hosted variable-weight font files
├── components/         # UI components (one file per component)
├── hooks/
│   ├── usePomodoroTimer.ts   # Timer state, cycle logic, stats persistence
│   └── useTheme.ts           # Light/dark theme state and persistence
├── utils/
│   └── dateKey.ts       # Date formatting helpers used for stats keys
├── constants.ts         # Shared app-wide constants
├── App.tsx              # Top-level layout and tab routing
└── main.tsx              # App entry point
```

## Data & privacy

All session history and preferences are stored locally in the browser via `localStorage` (`ludis-focus-history`, `ludis-focus-theme`). Nothing is sent to a server. Clearing your browser storage or using "Reset Stats" in the app permanently deletes this data.

## License

MIT — see [LICENSE](LICENSE).