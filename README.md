# Lazy Tri Tracker

A single-page tracker for the 140.6 mile November challenge:
Run/Walk 26.2 mi, Cycle 112 mi, Swim or Row 2.4 mi.

- Seven pages, one each for Brad, Brooke, Alice, Millie, Dean, Tessa and Guest (`#brad`, `#brooke`, ...), plus a family leaderboard.
- Log workouts in miles, kilometers, yards or meters.
- Weekly totals and a copyable tracking sheet.

## Running it

`index.html` is the whole app. Open it in a browser, or host it with GitHub Pages
(Settings, Pages, deploy from `main` / root).

## Shared family database (Firebase Realtime Database)

Without a database, each log is saved in that browser only. To share the leaderboard:

1. Go to https://console.firebase.google.com and create a new project (any name, analytics off).
2. Build, then **Realtime Database**, then **Create database**. Pick a location and start in locked mode.
3. Open the **Rules** tab, paste the rules below, and **Publish**.
4. Copy the database URL from the **Data** tab (looks like `https://NAME-default-rtdb.firebaseio.com`).
5. Paste it into `REMOTE_URL` near the top of the script in `index.html` and commit.

```json
{
  "rules": {
    "people": {
      ".read": true,
      "$id": {
        ".write": "$id === 'brad' || $id === 'brooke' || $id === 'alice' || $id === 'millie' || $id === 'dean' || $id === 'tessa' || $id === 'guest'"
      }
    }
  }
}
```

There is no login. Anyone who has the site address can read and edit any of the seven pages,
so keep the address within the family. The rules only allow those seven page names and nothing else.

When the page is opened inside claude.ai as an Artifact it uses claude.ai's own shared storage instead.
