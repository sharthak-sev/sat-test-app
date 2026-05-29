# SAT Interactive Practice App (Sub-App)

> [!WARNING]
> **This is a sub-application and is NOT functional on its own.**  
> It strictly requires a `.sat-test` question bank file, which must be exported using the **sat-qb-exporter** Chrome extension from an authenticated College Board session.

This is a standalone, offline, frontend-only practice environment designed to precisely replicate the official College Board **Bluebook** testing experience using your exported question banks.

## Workflow

1. Use the [sat-qb-exporter](https://github.com/sharthak-sev/sat-qb-exporter) extension to extract questions from your College Board account and click **Export as Interactive Test** to save a `.sat-test` file.
2. Open this app.
3. Click **Import .sat-test** and load the exported file.
4. Use **Create New Test** to start either:
   - **Custom Practice**: Single-subject practice focusing on specific areas with a per-question count-up timer.
   - **Full Adaptive Test**: Full test simulation mimicking Bluebook with RW Module 1, adaptive RW Module 2, a 10-minute break, Math Module 1, and adaptive Math Module 2 (scoring mimics item response theory).
5. Use **Retry Mistakes** to selectively practice only the questions you've previously gotten wrong or skipped.
6. Use **Past Tests** to review completed sessions, track time analytics per-question, and read explanations.

## Run Locally

Open `index.html` in a browser, or serve this folder with any static server:

```bash
python3 -m http.server 4173
```

Then visit `http://localhost:4173`.

No build step, package install, accounts, or backend servers are required. **Everything is strictly offline.**

## Data & Privacy

This app relies entirely on frontend technologies (HTML, CSS, JS) and uses **IndexedDB (Dexie.js)** to store all user history, question banks, and analytics locally on your device.

- `.sat-test` files include answer keys so the app can score your practice. **Treat exported files as private study material.**
- Your test history, timings, and custom practice data never leave your browser.
- Use the **Danger Zone** on the dashboard to wipe all stored local data at any time.
