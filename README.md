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
Walk 7 days (they already walk daily, so these are easy points) · Strong Day 3× · Mobility & Yoga 3× · Grip & Balance 5× per week. Strength is set above the CDC minimum for adults 65+, which is [muscle strengthening ≥2 days/week plus balance activities](https://www.cdc.gov/physical-activity-basics/guidelines/older-adults.html).

## Putting it online
Hosted with **GitHub Pages** straight from the `main` branch, with no build step (`.nojekyll` makes Pages serve the files exactly as they are). Every push to `main` redeploys in about a minute.

On the phone, open the URL and choose **Add to Home Screen**. It then opens like an app and works offline (videos still need internet).

## Customising
All content is at the top of the `<script>` in `index.html`:
- `EXERCISES`: steps, dose, tips. Set `video: 'https://youtu.be/…'` on any move to replace the default YouTube search with a specific video.
- `SESSIONS`: which moves go in each session.
- `CLASSES`: longer follow-along videos (add `video:` for an exact link).

## Why this works
Every exercise has a collapsible **Why this works** note, in the library and during sessions: which muscles it trains and what that does in daily life. They are general exercise physiology; a source is linked where a specific study is cited (e.g. PURE for grip strength). Cat-Cow and Seated Twist include an osteoporosis caution.

## Kitchen Corner
A new recipe every Monday (12 rotating), each with about 20–30 g of protein per serving and no added salt (low-sodium for blood pressure). Each recipe comes with a short "Science corner" note with a source link: protein per meal and per day for older adults, leucine, thirst with age, protein before bed, creatine, sodium, and protein after strength training. There's also a one-line daily habit on the Today screen, matched to each person's theme. Settings can hide the recipe.

## iPhone & iPad
- **Install from Safari:** Share (or ••• → Share) → Add to Home Screen. The app shows these steps itself until it's installed. Always open it from the icon: iOS keeps a home-screen app's data separate from Safari's, and protects it from Safari's automatic clean-up of website data.
- **One person logs for both.** Tap Dad / Mom / Both at the top. **Yesterday** backfills a missed day. **Did it without the app?** ticks off a session without going through the guide.
- **Text size** (A / A+ / A++), **High contrast** (darker text, thicker outlines, bolder type; light and dark) and a **color** for each person (8 choices) are in Settings. On iPad the layout widens to two and three columns.
- The screen stays awake during sessions and check-ins (Wake Lock, iOS 16.4+). Timer beeps follow the ring/silent switch.

## Known limitations
- **No automatic sync.** The iPhone and the iPad each keep their own copy. Settings → **Send my progress** → AirDrop, then **Add progress from a file** on the other device. Entries are merged, not overwritten. Pick one main device to avoid the chore.
- Video buttons open YouTube searches, not specific videos, because the links weren't verified when the app was built.
