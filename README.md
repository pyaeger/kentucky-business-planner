# Kentucky Business Planner

A mobile-friendly planner for finding workspace, finding customers, and checking what a job actually pays in Kentucky.

- **Live app:** https://pyaeger.github.io/kentucky-business-planner/
- Fully self-contained: one HTML file, no accounts, no analytics, no external requests.
- Works offline. Anything entered stays in the browser on the device.
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

## Files

- `index.html` — the entire app (markup, styles, content, logic)
