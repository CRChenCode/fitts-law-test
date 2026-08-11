# Fitts Law Test

A browser-based Fitts' law pointing task that records participant results to Google Sheets and can be published as a static GitHub Pages site.

## Local Development

Install dependencies:

```bash
yarn
```

Run the app locally:

```bash
yarn start
```

Build the GitHub Pages version:

```bash
yarn build:pages
```

The built site is written to `docs/`. Configure GitHub Pages to serve the `main` branch from `/docs`.

## Google Sheets Configuration

The deployed app currently keeps the Google API key, OAuth client ID, and Sheet ID in public browser code.

To use another Google Sheet:

1. Create a sheet with these tabs: `Runs`, `RunAverages`, and `UserAverages`.
2. Update every `spreadsheetId` in `src/app/app.service.ts`.
3. Update the helper `spreadsheetId` in `src/index.html`.
4. If changing Google credentials, update `CLIENT_ID` and `API_KEY` in `src/index.html`.
5. Run `yarn build:pages` and commit the updated `docs/` files.

If you need to patch production before a rebuild works, make the same credential and Sheet ID edits in `docs/index.html`.
