# The Lever Pull

A weekly feed of digital marketing news for the team: one short summary of the week, then the stories that matter, each with a takeaway (“Do:” when someone needs to act, “Watch:” otherwise).

## What’s in this repo

| Path | What it is |
| --- | --- |
| `index.html` | The feed page. Works on GitHub Pages or any static host. |
| `data/index.json` | The list of weeks to show, by date. |
| `data/issues/<date>.json` | One file per week. |
| `templates/new-week.json` | A blank week to copy. |
| `claude-artifact/the-lever-pull.html` | The original Claude artifact version, kept for reference. It only works inside Claude. |

## Publish it with GitHub Pages

1. Push this folder to a GitHub repository (see below).
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, and save.
4. After a minute or two, GitHub shows the page’s address at the top of that settings page.

GitHub Pages sites are public on free plans, even when the repository is private. Organization plans can restrict who can view the site.

## Add a new week

1. Copy `templates/new-week.json` to `data/issues/YYYY-MM-DD.json`, using that Monday’s date.
2. Fill in `publishedAt` (same date), `weekOf` (for example `Oct 19–26, 2026`), `intro`, and the stories.
3. Add the date to `data/index.json`, for example `["2026-10-26", "2026-10-19"]`.
4. Commit and push. The page always opens on the newest week; older weeks stay in the dropdown.

Story fields:

- `id`: any unique short id within the week, like `s1`, `s2`
- `category`: one of `search`, `paid-search`, `social`, `paid-social`, `analytics`, `commerce`
- `source`, `url`, `title`, `summary`
- `takeaway`: one sentence
- `needsAction`: `true` shows the takeaway as “Do:”, `false` as “Watch:”

## Preview on your computer

Browsers block the page from loading its data files when you double-click `index.html`. Run a small local server from this folder instead:

```
python3 -m http.server 8000
```

Then open http://localhost:8000.
