# Lazy Tri Tracker

A single-page tracker for the 140.6 mile November challenge:
Run/Walk 26.2 mi, Cycle 112 mi, Swim or Row 2.4 mi.

- Seven pages, one each for Brad, Brooke, Alice, Millie, Dean, Tessa and Guest (`#brad`, `#brooke`, ...), plus a family leaderboard.
- Log workouts in miles, kilometers, yards or meters.
- Weekly totals and a copyable tracking sheet.

## Running it

`index.html` is the whole app. Open it in a browser, or host it with GitHub Pages
(Settings, Pages, deploy from `main` / root).

Saving: on its own, each person's log is saved in that browser only (`localStorage`).
When the page is opened inside claude.ai as an Artifact, it also saves to the shared
family database so the leaderboard works across devices. The GitHub Pages copy has no
shared database, so the leaderboard shows only what is in the current browser.
