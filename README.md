# Strong Together

A friendly, phone-first fitness tracker for two older adults. It covers strength, grip, balance, chair yoga and walking. It is one static HTML file with no build step, no backend and no accounts. Data is saved on the device (`localStorage`).

## What's in it
- **Today**: tap who is exercising (Dad / Mom / Both), log a walk with one tap, start a guided session (Strong Day ~15 min, Yoga & Stretch ~12 min, Grip & Balance ~6 min), see weekly goal rings and a week "garden".
- **Guided player**: one move per screen with large text, a built-in timer with a beep and vibration, easier and harder options, a safety tip and a **Watch how** video button. Afterwards it asks "How did that feel?" and uses the answer to suggest making things harder or easier.
- **Exercises**: the full library plus longer follow-along classes.
- **Progress**: monthly check-ins with a 30-second chair stand (tap-to-count, 30 s countdown, compared with the CDC STEADI reference for age and sex), grip strength (needs a cheap hand dynamometer) and one-foot balance. Trend charts, a 6-week history, and **Send this week's update to family** (uses the phone's share sheet).
- **Trophies**: points, levels (Sprout → Shooting Star), 15 badges and a bonus for exercising together.
- Settings for names, ages, weekly goals, light/dark theme, and backup/restore to a file.

## Default goals (editable)
Walk 6 days · Strong Day 2× · Yoga & Stretch 3× · Grip & Balance 5× per week. The strength minimum follows the CDC guidance for adults 65+: [muscle strengthening ≥2 days/week plus balance activities](https://www.cdc.gov/physical-activity-basics/guidelines/older-adults.html).

## Putting it online
Hosted with **GitHub Pages** straight from the `main` branch, with no build step (`.nojekyll` makes Pages serve the files exactly as they are). Every push to `main` redeploys in about a minute.

On the phone, open the URL and choose **Add to Home Screen**. It then opens like an app and works offline (videos still need internet).

## Customising
All content is at the top of the `<script>` in `index.html`:
- `EXERCISES`: steps, dose, tips. Set `video: 'https://youtu.be/…'` on any move to replace the default YouTube search with a specific video.
- `SESSIONS`: which moves go in each session.
- `CLASSES`: longer follow-along videos (add `video:` for an exact link).

## Known limitations
- Data lives on one device. If both parents use the app, one shared phone or tablet with the "Both" button works best. Two separate phones won't sync. Use Backup/Restore to move data.
- Video buttons open YouTube searches, not specific videos, because the links weren't verified when the app was built.
