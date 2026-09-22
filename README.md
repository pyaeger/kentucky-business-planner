# Kentucky Trades Planner

A mobile-first planner for self-employed trades work in the Lexington–Louisville corridor: finding shared bay space, finding steadier customers, knowing what a job actually leaves, and five AI interviews that ask about your situation before they advise.

- **Live app:** https://pyaeger.github.io/kentucky-trades-planner/
- One HTML file. No accounts, no analytics, and no third-party requests on page load.
- Anything entered stays in the browser on the device (`localStorage`); nothing is sent anywhere.
- **Not currently offline-capable.** There is no service worker, so the page needs a connection to load. See *Known limitations*.
- Install on iPhone: open the link in Safari → Share → **Add to Home Screen**.

## What it covers

Eight tabs:

- **Next steps** — a 30-day plan built around making $500/month repeatable before committing to space
- **Garage** — four routes to workspace, from a scheduled shared bay to working at approved customer sites, with what to say when you ask
- **Customers** — named local prospects, three customer groups to test, and scripts for a first small ask
- **Money** — what a job actually leaves after costs, and glass compared fairly against painting
- **Resources** — SBDC offices, trade associations and agency contacts with phone numbers
- **Opportunities** — copy-ready offers for dealers, contractors, turnover painting and route work
- **AI prompts** — five structured interviews (below)
- **About** — colophon, sources, and what the app does not do

Contact and location information is public data, checked September 19, 2026.

## The AI interviews

Five copy-paste prompts. Each one interviews you — exactly five questions, one at a time, labelled `Question 1 of 5` so you can tell if the AI is skipping ahead — then produces a plain-text `MY NEXT STEPS` block you paste back into the planner, edit, and tick off.

| | |
|---|---|
| Decide what to tackle first | which problem is actually blocking paid work |
| Build a work week that holds | jobs, travel, quoting, supplies, payment chasing |
| Keep the work reachable | vehicle, tools, workspace, travel cost |
| Handle a hard customer conversation | quoting, scope creep, unpaid invoices, saying no |
| Choose what to test next month | one direction, an honest tradeoff, a review date |

The prompts are built mostly out of **negative** constraints — what the model must not assume:

> Base your suggestions on my actual time, money, energy, commitments, skills, and support. Separate what I told you from estimates and unknowns. Prefer small, affordable, reversible actions. Do not invent earnings, demand, appointments, personal history, diagnoses, or eligibility.

> Do not assume I lack a vehicle, licence, tools, or workspace.

> If I say "I don't know" or "skip", accept that and count the question as answered. Do not invent a fact to fill the gap.

> Do not say you have saved anything to my planner or contacted anyone.

A planning tool used by someone short on money and time should not fabricate numbers, and should say plainly which figures came from the user and which are guesses. The app itself never sends your answers anywhere — but the AI service you paste into does receive them, and the app says so on the page.

## Verification

**[trades-planner-verification.md](trades-planner-verification.md)** records
every phone number in the app, checked 2026-09-21 against each organisation's
own website or an independent directory, with a confidence grade each.

15 of 18 confirmed correct, no errors found. Three could not be checked from an
automated request and are marked as unchecked rather than assumed good. It also
records one ambiguity — Medley's Auto Care has four Louisville branches and the
app does not say which one it lists.

## Licence

MIT. See [LICENSE](LICENSE). The contact and location data is public
information published by the organisations themselves.

## Known limitations

Verified by reading the source, September 2026.

| Claim | Status | Confidence |
|---|---|---|
| No third-party requests on page load | True — no external `script`, `link`, `img` or `fetch`. | H |
| Entered data stays on the device | True — `localStorage` only, no network calls. | H |
| Works offline | **False today.** No `sw.js` and no service-worker registration, so the page needs a connection to load. Saved data survives; the app itself will not open. | H |
| Contacts were checked on a stated date | True — the colophon and resource tabs both carry "checked September 19, 2026". | H |
| Those contacts are current *now* | **Unverified since that date.** 18 phone numbers, named local businesses and agency offices. Openings, prices, permissions and eligibility all still need confirming by phone before travelling. | L |
| Commercial listings are current | **No.** Bay and workspace listings are live inventory and rot fast. Confirm availability before making a trip. | H |

The app links out to roughly two dozen external sites — agencies, chambers of commerce, local services and AI assistants. Those are links the user chooses to follow, not requests the page makes.

## Files

- `index.html` — the entire app (markup, styles, content, logic)
