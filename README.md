# D&D 3.5e Encounter Engine

A mobile-friendly, installable Progressive Web App (PWA) for generating reusable D&D 3.5e encounter prompts across campaign settings.

## Features

- Generate monsters, groups, traps, treasure, NPCs, hazards, dungeon features, and random events.
- Configure target CR or average party level, party size, difficulty, creature type, environment, and setting.
- Select multiple campaign settings or leave settings unrestricted.
- Add custom monsters, NPCs, traps, treasure, and hazards.
- Random monster decision button and DM quick-roll tools.
- Create campaign profiles and save generated encounters.
- Export/import a JSON backup of homebrew, campaigns, and saved encounters.
- Offline PWA support after the first successful load (served over HTTPS or localhost).

## Run locally

The service worker requires localhost or HTTPS. From this folder:

```bash
python -m http.server 8000
```

Open <http://localhost:8000>.

## Publish to GitHub Pages

1. Create a new GitHub repository.
2. Upload the contents of this folder to the repository root (not the containing folder).
3. Open **Settings → Pages**.
4. Under **Build and deployment**, choose **Deploy from a branch**.
5. Select `main` and `/ (root)`, then save.
6. Wait for GitHub Pages to publish. Open the Pages URL on your phone.
7. In Chrome on Android, use **⋮ → Add to Home screen** or **Install app** if offered.

If the app is hosted in a repository subfolder, the included relative paths still work when the repository's Pages URL serves that folder as its root. If you change the app's base path or filename, update `start_url`, `scope`, and the service worker asset paths accordingly.

## Data storage and privacy

User-created entries, campaign profiles, and saved encounters are stored in the browser's `localStorage` on that device. They are not automatically synced to GitHub or other devices. Use **Campaigns → Export JSON backup** to back up or transfer your data. Import the backup on another device.

Do not clear browser site data unless you have exported a backup.

## Important rules/content limitations

This is an independent fan-made utility, not an official Dungeons & Dragons product. The bundled creature data is intentionally a small starter sample, not a complete Monster Manual or full compendium of 3.5e publications. Some sample records are abbreviated and must be checked against the original stat block. The generator's encounter group, CR adjustments, treasure, trap, and NPC outputs are prompts or estimates—not guaranteed rules-accurate calculations. Verify encounter level, XP, treasure budgets, and stat blocks using the official 3.5e rules and your campaign sources.

The app does not include copyrighted sourcebook text. Add your own legally usable notes and homebrew data.

## Project files

- `index.html` — app interface and styles
- `app.js` — generator, local storage, library, campaign manager, tools
- `manifest.webmanifest` — installable app metadata
- `sw.js` — offline caching service worker
- `icon.svg` — app icon

## License

MIT for the original code in this repository. This license does not grant rights to Dungeons & Dragons trademarks or third-party game content.
