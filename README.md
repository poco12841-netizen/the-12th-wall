# THE 12TH WALL
**Seattle Seahawks · 2026 Defensive Intelligence Center**

An open-source, cinematic fan data explorer. Unofficial and not affiliated with the NFL or Seattle Seahawks.

## Stack
- React + TypeScript + Vite
- Recharts and Lucide
- Python + Pandas data preparation
- GitHub Actions for data refresh and GitHub Pages deployment

## Run locally
```bash
npm install
npm run dev
```

## Generate the verified 2026 data snapshot
Python 3.10+ is required.
```bash
pip install pandas requests
python scripts/build_data.py
```
The script downloads public regular-season team, player and play-by-play CSV releases from nflverse and writes `public/data/seahawks-2026.json`.

## Publish
1. Create a GitHub repository named `the-12th-wall`.
2. Push this folder to the `main` branch.
3. In repository Settings → Pages, choose GitHub Actions as the build source.
4. The included `Deploy to GitHub Pages` workflow builds and publishes the app.
5. The `Refresh Seahawks data` workflow can be run manually, and is scheduled weekly.

## Data integrity
- No placeholder statistics are shown as real values.
- The interface displays an explicit data-pipeline warning until a generated snapshot exists.
- Play-by-play is used for play context and opponent EPA.
- Tracking-based player coordinates are not inferred; the field formation shown in the Playground is explicitly schematic.
- Metric availability depends on the fields present in the upstream public release. Missing fields remain blank.

## Sources
- [nflverse play-by-play loader](https://nflreadr.nflverse.com/reference/load_pbp.html)
- [nflverse data schedule](https://nflreadr.nflverse.com/articles/nflverse_data_schedule.html)
- [nflverse automated data releases](https://github.com/nflverse/nflverse-data)
- [Seattle Seahawks official statistics](https://www.seahawks.com/team/stats/2026/reg)
- [NFL Next Gen Stats methodology](https://support.nfl.com/hc/en-us/articles/35869706651156-NFL-Pro-FAQ-s-and-Answers)

## License
MIT for this project code. Upstream data and third-party assets remain subject to their own terms and licenses.
