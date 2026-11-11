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

## Voice coach
Tap 🔊 in any session and a coach reads each move aloud, gives the weights, counts reps at a controlled pace ("Count with me"), and calls out timers, so nobody has to look at the screen. Recipes have "Read aloud" too. Six coaches, each with their own accent, speed, pitch and script:

| Coach | | Accent | Personality | iPhone/iPad voice |
|---|---|---|---|---|
| Maggie | F | Irish | Warm and brisk | Moira |
| Arthur | M | British | Dry wit, likes the science | Daniel |
| Sunny | F | Australian | Bubbly and energetic | Karen |
| Hank | M | American | Laid-back and easygoing | Fred / Aaron |
| Tessa | F | South African | Calm, like a yoga teacher | Tessa |
| Raj | M | Indian | Encouraging, a stickler for form | Rishi |

Uses the device's built-in voices (Web Speech API), so nothing is sent anywhere. If a voice isn't installed, the coach falls back to the closest English voice of the same gender; better voices can be downloaded in iOS Settings → Accessibility → Spoken Content → Voices.

## Floor Confidence and Everyday wins
A weekly **Floor Confidence** session practises getting up from the floor in stages (kneel at the sofa → half-kneel to stand → floor to chair), following the NHS sequence, with a safety check first and an "If you ever fall" plan at the end. **Hammer Turns** (forearm rotation) were added to Grip & Balance for opening jars. **Everyday wins** on the Progress screen are real-life milestones (open a new jar, get up from the floor, play the accordion standing…) worth 25 points each.

## Back care, upper body and nutrition (November 2026)
Built from family feedback: back care, stiffness, more upper-body strength, and high-fibre, low-salt nutrition. Personal details are entered on the device, not stored here.
- **Heights and weights** are entered in Settings and stay on the device (never in this repo) and drive a **daily guide** in Kitchen Corner for each person: protein 1.0–1.2 g/kg (PROT-AGE), fibre adequate intake for 51+ (Health Canada: 21 g women, 30 g men), sodium under 1,500 mg (AHA ideal). A lean build gets a "eat enough, not less" note.
- **Back care** (Settings, per person, off by default): back-friendly versions shown on rows, twists, forward bends, leg swings and the floor session.
- **Morning Loosen-Up**: a daily 5-minute gentle mobility session for stiffness, including seated pelvic tilts.
- **Upper Body Day**: arm circles, counter push-ups, supported rows, curls, side raises, optional overhead press, shoulder-blade squeezes. Suggested Thursdays; Strong Day Mondays and Saturdays.
- **Recipes**: 16 now, every one high-fibre and with no added salt, showing protein and fibre per serving; new science notes on fibre and on oat/barley beta-glucan.

## Dumbbell weights
Arm Curls, Supported Row and Overhead Press use dumbbells; Sit-to-Stand can add one later. Each person has their own weight per exercise (stored in lb, shown in lb and kg), adjusted with − / + during a Strong Day. Progression rule: 2 rounds of 8–12; when 12 feels easy on both rounds, go up one step (0, 1, 2, 3, 4, 5, 6, 8, 10, 12, 15, 20 lb). Starting defaults: Dad 5 lb curls/rows and 3 lb press, Mom 3 lb and 2 lb. The weights used are saved with each Strong Day, and Progress shows the increase since the first one.

## Why this works
Every exercise has a collapsible **Why this works** note, in the library and during sessions: which muscles it trains and what that does in daily life. They are general exercise physiology; a source is linked where a specific study is cited (e.g. PURE for grip strength). Cat-Cow and Seated Twist include an osteoporosis caution.

## Kitchen Corner
A new recipe every Monday (12 rotating), each with about 20–30 g of protein per serving and no added salt (low-sodium for blood pressure). Each recipe comes with a short "Science corner" note with a source link: protein per meal and per day for older adults, leucine, thirst with age, protein before bed, creatine, sodium, and protein after strength training. Settings can hide the recipe.

## iPhone & iPad
- **Install from Safari:** Share (or ••• → Share) → Add to Home Screen. The app shows these steps itself until it's installed. Always open it from the icon: iOS keeps a home-screen app's data separate from Safari's, and protects it from Safari's automatic clean-up of website data.
- **One person logs for both.** Tap Dad / Mom / Both at the top. **Yesterday** backfills a missed day. **Did it without the app?** ticks off a session without going through the guide.
- **Text size** (A / A+ / A++), **High contrast** (darker text, thicker outlines, bolder type; light and dark) and a **color** for each person (8 choices) are in Settings. On iPad the layout widens to two and three columns.
- The screen stays awake during sessions and check-ins (Wake Lock, iOS 16.4+). Timer beeps follow the ring/silent switch.

## Known limitations
- **No automatic sync.** The iPhone and the iPad each keep their own copy. Settings → **Send my progress** → AirDrop, then **Add progress from a file** on the other device. Entries are merged, not overwritten. Pick one main device to avoid the chore.
- Video buttons open YouTube searches, not specific videos, because the links weren't verified when the app was built.
