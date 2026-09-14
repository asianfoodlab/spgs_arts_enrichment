# SPGS Arts & Enrichment — 2026/27 programming

Planning tool for the St Paul's Girls' School Arts & Enrichment co-chairs.

## What's here

`spgs-programme-planner.html` — a self-contained season board:

- **Timeline** — every candidate event drawn to scale across Sep 2026 – Jul 2027,
  against school terms, half terms, holidays and notable religious/cultural days.
- **Shortlist** — each event scored 1–5 on proximity to Brook Green, novelty for an
  audience that has seen most things, quality, and bespoke-access potential.
- **Slate** — a term-by-term proposal that clears the "one arts + one enrichment
  per term" rule.
- **Deadlines** — the dated decisions, earliest first.

Published as an artifact; republish the same file path to update it in place.

## Editing

All data lives in the `EVENTS`, `TERMS`, `BREAKS`, `NOTABLE` and `SCHOOL` arrays in the
`<script>` block at the bottom of the file. Add an event by appending one object to
`EVENTS`; the timeline, the filters and the scored table all rebuild from it.

```js
{n:"Event name", v:"Venue", cat:"arts"|"enrich"|"family", src:"list"|"new",
 from:"2026-10-02", to:"2027-01-31", mi:3.9, s:[near, unseen, quality, bespoke],
 pick:true,            // optional — outlines the bar as part of the recommended slate
 open:true,            // optional — year-round, draws a dashed full-width bar
 why:"One line on the angle."}
```

## Known gaps

- The Google calendar named *SPGS* is a shared family calendar, not the school's.
  Parents' evenings, concerts, Founder's Day and school productions are **not** in
  this view. The school calendar is linked from each Friday Bulletin, behind a login.
- Term dates come from published term-date listings, not the school site directly.
- Islamic and Hindu festival dates are marked `~` and are approximate.
- Distances are straight-line from W6 7BS.

## Day-by-day evening planner

`school-year-evenings.csv` — one row per day, 4 Sep 2026 to 8 Jul 2027 (308 days).
Live as a Google Sheet in wongkaren@gmail.com's Drive:
https://docs.google.com/spreadsheets/d/1Ikw9cVv1_8-rHjemp_2hcXEXx73EBZNPd6njpxcAk40/edit

Source: the **"St Paul's Girls' School calendar"** subscribed feed
(`k8j2v9hs5krtqilik3qa900cenh4bqor@import.calendar.google.com`) — 638 events across
the year, 103 of them starting 17:00 or later. Times converted to Europe/London.
Term and half-term boundaries come from the school's own markers in that feed.

| Col | Contents |
|-----|----------|
| A   | Date |
| B   | Month, as `2026-09 Sep` so the filter dropdown sorts chronologically |
| C–D | Weekday, term week |
| E–F | Period and machine-readable status (Term / Break) |
| G   | Notable day — UK and Jewish festivals exact, Islamic/Hindu "(approx)" |
| H   | School evening events, 17:00+, with times |
| I   | How many that evening |
| J   | Daytime and all-day school context: trips, exam weeks, Reading Weeks |
| K   | Other commitment — blank, for the committee |
| L   | `free` / `BOOKED`, from I and K |
| M   | `OPEN` on term-time Tue/Wed/Thu with nothing on and no festival |

L and M are array formulas in row 2 only — don't type in those columns.

**45 prime Tue/Wed/Thu evenings** across the year. By month: Sep 4, Oct 2, Nov 4,
Dec 3, Jan 4, Feb 6, Mar 3, Apr 1, May 9, Jun 7, Jul 2.

Snapshot, not a live sync — the school feed changes.
