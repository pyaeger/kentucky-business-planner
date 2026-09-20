# Kentucky Business Planner

A mobile-friendly planner for finding workspace, finding customers, and checking what a job actually pays in Kentucky.

- **Live app:** https://pyaeger.github.io/kentucky-business-planner/
- One HTML file. No accounts, no analytics, and no third-party requests on page load.
- Anything entered stays in the browser on the device (`localStorage`); nothing is sent anywhere.
- **Not currently offline-capable.** There is no service worker, so the page needs a connection to load. See *Known limitations*.
- Install on iPhone: open the link in Safari → Share → **Add to Home Screen**.

## What it covers

- **Workspace** — where to work from, by city
- **Customers** — how to find the first ones without a budget
- **Income between jobs** — Kentucky Career Center locations with addresses and phone numbers, by city
- **Earnings checks** — what a given job or gig actually nets, before deciding it is worth the commute

All location and contact information is public agency data.

## On the built-in AI guidance

The planner carries its own instructions for any AI assistant used alongside it. They are deliberately restrictive:

> Base your suggestions on my actual time, money, energy, commitments, skills, and support. Separate what I told you from estimates and unknowns. Prefer small, affordable, reversible actions. Do not invent earnings, demand, appointments, personal history, diagnoses, or eligibility.

The point is that a planning tool used by someone short on money and time should not fabricate numbers, and should say plainly which figures came from the user and which are guesses.

## Known limitations

Verified by reading the source, September 2026.

| Claim | Status | Confidence |
|---|---|---|
| No third-party requests on page load | True — no external `script`, `link`, `img` or `fetch`. | H |
| Entered data stays on the device | True — `localStorage` only, no network calls. | H |
| Works offline | **False today.** No `sw.js` and no service-worker registration, so the page needs a connection to load. Saved data survives; the app itself will not open. | H |
| Agency addresses and phone numbers are current | **Unverified.** Taken from public agency listings and not re-checked against the sources since. Career Center locations and hours do change. | L |

The app links out to roughly two dozen external sites — agencies, chambers of commerce, local services and AI assistants. Those are links the user chooses to follow, not requests the page makes.

## Files

- `index.html` — the entire app (markup, styles, content, logic)
