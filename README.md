# 🏋️‍♂️ Workout Routine Generator

A React web app that generates a personalized weekly workout routine from your age, fitness level, goal and available days, and keeps your history and progress in the browser.

## Features

**Working today**
- Routine generation by level (beginner / intermediate / advanced) and goal (lose weight / gain muscle / stay fit), adjusted with your feedback and nutrition notes (`src/utils/routineGenerator.js`).
- Workout history and basic progress stats, stored locally in `localStorage`. No account and no server.
- Notifications, loading states and an error boundary, with global state managed through React Context (`src/context/AppContext.js`).
- Camera view (`CameraExerciseTracker`). It opens the webcam, but **exercise recognition and rep counting are simulated** with random values. It is a placeholder for a future TensorFlow.js / MediaPipe integration.

**Planned (not wired into the app)**
`src/_futuro/` holds draft components for upcoming features: wearables, gamification (rewards, weekly challenges, progress chart), nutrition and mindfulness forms, social sharing, special populations, an equipment-free routine, a weekly planner and active-break reminders. Nothing imports them yet. See [ROADMAP.md](ROADMAP.md) for the long-term plan.

## Getting started

Requires Node.js 16 or newer.

```bash
git clone https://github.com/joan-bl/workout-routine-generator.git
cd workout-routine-generator
npm install
npm start          # http://localhost:3000
```

| Script | What it does |
|---|---|
| `npm start` | Development server |
| `npm test` | Tests in watch mode (`src/tests/`) |
| `npm run test:coverage` | Tests once, with a coverage report |
| `npm run build` | Production build in `build/` |
| `npm run serve` | Serves the production build locally |
| `npm run lint` | ESLint |

## Project structure

```
src/
├── App.js                  # Main screen
├── components/             # Components used by the app
│   ├── RoutineForm.jsx
│   ├── RoutineResult.jsx
│   ├── CameraExerciseTracker.jsx
│   ├── NotificationSystem.jsx
│   ├── LoadingSpinner.jsx
│   └── ErrorBoundary.jsx
├── context/AppContext.js   # Global state (Context API)
├── utils/                  # Routine generator, persistence, error helpers
├── tests/                  # Jest + React Testing Library
├── assets/                 # Logo and banner
└── _futuro/                # Draft components, not used yet
design/                     # Logo and banner source files (InDesign)
```

To add or change exercises, edit `EXERCISES` in `src/utils/routineGenerator.js`.

## License

MIT. See [LICENSE](LICENSE).
