# leo-content

Remote content for **The LEO** — the official mobile app of Saint Mark the
Evangelist Catholic Church in Birmingham, AL.

These JSON files are fetched by the app on launch. Updating them updates the
app without needing a new build or store submission.

| File | What it controls |
|------|------------------|
| `letters.json` | Latest "Leo Letter" (pastor's message) shown on the Home tab |
| `novenas.json` | Active novena / devotion shown on Home when today is in the window |

## How to update a Leo Letter

1. Open `letters.json`
2. Replace the first object in `posts` with the new letter, or add a new one at the top
3. Commit + push → app picks up the change within ~6 hours of cold launch

## How to start a novena

1. Open `novenas.json`
2. Add an object to the `novenas` array. Required fields:
   - `slug` (e.g., `"sacred-heart"`)
   - `name` (display title)
   - `feast` (optional)
   - `windows` — array of `{start, end}` ISO dates (the dates when the card is shown)
   - `intro` — short blurb on the Home card
   - `openingPrayer`, `closingPrayer` (optional)
   - `days` — array of `{day, title, body}` for each of the 9 days
3. Commit + push

The Home tab will automatically show the novena card during any active window.
