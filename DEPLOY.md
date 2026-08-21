# davidturns7 — deployment manifest

Repo: github.com/Cfc20/davidturns7 · Branch: `master` · Live: https://cfc20.github.io/davidturns7

## Files that must be in the repo root

| File | Source | Status |
|---|---|---|
| `index.html` | provided by Claude | ready |
| `preview.jpg` | provided by Claude | ready |
| `event.ics` | provided by Claude | ready |
| `spider.png` | **YOUR drawing — you upload this** | MISSING |
| `.github/workflows/static.yml` | already in repo | done |

## Why the favicon is blank right now

`index.html` line 17–18 points the browser icon and the iPhone home-screen icon at
`spider.png`. That file is not in the repo, so there is nothing to load.

Upload `spider.png` and the favicon appears. No code change needed.

## What each file does

- **index.html** — the invite page. References `spider.png` (hero + RSVP button + favicon)
  and `event.ics` (calendar buttons).
- **preview.jpg** — the image that shows in text-message and social link previews.
  Referenced by absolute URL in the `og:image` tag, cache-busted at `?v=9`.
- **event.ics** — Apple/Outlook calendar file. Google Calendar uses a direct link, no file.
- **spider.png** — your artwork. Drives hero, RSVP button, browser tab, home-screen icon.

## Requirements for spider.png

- Filename exactly `spider.png` — lowercase, no spaces. GitHub is case-sensitive.
- PNG format. If yours is a .jpg, either convert it or tell Claude to change the reference.
- Transparent or white background both work; CSS inverts it to white on the dark sections.

## Upload steps

1. github.com/Cfc20/davidturns7 → **Code** tab
2. **Add file** → **Upload files**
3. Drag in: `index.html`, `preview.jpg`, `event.ics`, `spider.png`
4. **Commit changes**
5. **Actions** tab — wait for the green check (about 1 minute)

## Verify after deploy

1. Load https://cfc20.github.io/davidturns7 — spider shows at top
2. Browser tab shows the spider icon
3. Tap the red button — messages app opens with the RSVP prefilled
4. Tap "Searcy Swim Center" — maps app opens with directions
5. Tap GOOGLE / APPLE — event lands on the calendar, Aug 29 2026, 5:30–7:30 p.m. CDT
6. Text yourself `https://cfc20.github.io/davidturns7/?v=9` — preview card renders

## Notes

- Preview images cache hard in iMessage. Change the `?v=` number to force a refresh.
- `preview.jpg` has no spider on it. It is a flat generated image; adding your artwork
  to it requires editing the JPG directly (Canva, Preview, etc.) and re-exporting at
  1200×630 with the same filename.
