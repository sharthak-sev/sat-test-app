# SAT Interactive Practice App

Standalone, frontend-only practice app for `.sat-test` files exported by the Chrome extension.

## Run

Open `index.html` in a browser, or serve this folder with any static server:

```bash
python3 -m http.server 4173
```

Then visit `http://localhost:4173`.

No build step, package install, account, or backend server is required. Data is stored locally in IndexedDB.

`.sat-test` files include answer keys so the app can score practice locally. Treat exported files as private study material.

## Workflow

1. Use the extension button **Export as Interactive Test** to save a `.sat-test` file.
2. Open this app.
3. Click **Import .sat-test**.
4. Use **Create New Test** to start either:
   - Single-subject custom practice with a per-question count-up timer.
   - Both-subject full test mode with RW Module 1, adaptive RW Module 2, a one-time 10-minute break, Math Module 1, and adaptive Math Module 2.
5. Use **Past Tests** to review completed full tests or subject tests, filter to missed questions, and view explanations and per-question time.

## Local Data

The app stores these IndexedDB tables:

- `questionBanks`: imported files and metadata.
- `questions`: normalized imported question data.
- `sessions`: completed test summaries.
- `responses`: per-question answers, correctness, timing, subject, domain, and skill.

Use **Reset Local Data** from the app header to clear everything stored in this browser.
