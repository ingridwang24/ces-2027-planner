# CES 2027 Session Planner

An interactive, single-page planner for CES 2027 (Las Vegas, Jan 6–9, 2027). It shows sessions across all 31 CES themes as a color-coded timetable, maps every venue with walking distances, flags schedule conflicts, and recommends which pass to buy.

## Who it's for

- **First-time CES attendees** who want to see the whole show by theme and venue.
- **People deciding which pass to buy** before early pricing ends Nov 30, 2026.
- **Product, strategy and BD people** covering several themes in one trip without double-booking.
- **Anyone splitting time across campuses** who wants to group days by area.

It's less useful for exhibitors working a booth all week, or anyone who only needs the show floor and keynotes.

**Live site:** https://ingridwang24.github.io/ces-2027-planner/

## Features

- **Timetable view:** sessions by day, laid out by time and venue, colored by theme.
- **Table view:** every session in a sortable table.
- **Filters:** theme (with "My 9 interests" and "All themes" presets), day, pass type, confirmed vs. projected, and text search.
- **My plan + Plan B:** two shortlists. My plan holds first choices and warns about overlaps and too-tight transfers between campuses. Plan B holds backups and shows which My plan session each one could replace. Move sessions between lists with one click, and copy both lists as text.
- **Add to calendar:** per-session links for Google Calendar, Outlook.com and Outlook (work/Microsoft 365), plus a downloadable `.ics` file of either list for Lark, Outlook desktop, Apple Calendar or Google import. Times are Pacific.
- **Pass recommender:** suggests Standard, Standard + add-ons, or Premium for each list, and shows what the other list would need. Prices are the official CES 2027 rates.
- **Venue map:** a schematic map of the Strip with LVCC, Venetian/Palazzo, Sphere, ARIA (C Space) and Fontainebleau. Each venue card lists its themes, sessions, address, a Google Maps link and directions.
- **Distance table:** walking distance, walking time and show-week ride time between every pair of venues.
- Works in light and dark mode and on phones. Your plan is saved in your browser (`localStorage`).

## Run it

It's one static HTML file with no build step:

```bash
open index.html
```

Or serve it locally:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000. It also works as-is on GitHub Pages.

## Data status (as of Oct 12, 2026)

CTA has not yet published the session-by-session CES 2027 agenda.

- **Confirmed** items come from CES 2027 announcements: the Jan 6 keynotes (CTA State of the Industry, Stellantis, Waymo, Lenovo at Sphere), CES Foundry (Fontainebleau, Jan 6–8), the add-on tracks (Digital Hollywood, Connect2Car, Quantum Means Business, The Spoon Food Tech Summit, Novaspace) and the StoryTech show floor tours.
- **Projected** items are placeholder slots for each theme. Their days, rooms and topics follow the CES 2026 program and will change.
- Tour times, tour prices and CES Foundry pass access are not yet published.
- Walking distances and ride times are estimates. Add 20–30% during show crowds.

Check everything against [ces.tech](https://www.ces.tech/) before you buy a pass or book travel.

## Updating the data

All data lives in `index.html`:

- `THEMES`: theme names and colors
- `VENUES` / `VENUE_ORDER`: venues and timetable columns
- `S`: the session list (day, start, end, theme, title, venue, room, pass access, status, notes)
- `DIST`: distances and times between venues
- `PINS`: map pin positions

## Sources

- [CES Registration Information](https://www.ces.tech/attendee-guides/registration-information/)
- [CES Conference Program](https://www.ces.tech/attend/conference-program/)
- [CES Topics](https://www.ces.tech/topics/)
- [CES Show Floor Tours](https://www.ces.tech/explore-ces/show-floor-tours/)
- [CES Foundry](https://www.ces.tech/explore-ces/ces-foundry/)
- [audioXpress: CES 2027 Returns January 6–9](https://audioxpress.com/news/ces-returns-january-with-ai-connected-mobility-and-new-opportunities-for-audio)

Not affiliated with CTA or CES.
