# apat-events

A Place at the Table's events, copied from Radiant's live setup (github.com/Chadbohi/radiant-events).

- `sync.py` reads APAT's public Church Center calendar (aptc.churchcenter.com, no key) every 30 minutes and commits `events.json` + `events.ics` (workflow "Sync Church Center events"). Past events go back 5 years (Church Center has APAT events from April 2023). Street addresses show only for church places; homes show their name.
- GitHub Pages serves the repo: https://legacyco.github.io/apat-events/events.json, `/events.ics` (Subscribe), `/preview.html` (every embed with live data).
- `embed/apat-events.js` goes once in Squarespace: Settings > Developer tools > Code Injection > Footer, inside `<script>...</script>`. Then each spot is a Code Block with one div:
  - Events page: `<div data-apat-events="full"></div>` (Upcoming + Past tabs, Show more, Subscribe)
  - Home: `<div data-apat-events="grid" data-count="3"></div>`
  - Kids section (Visit page): `<div data-apat-events="grid" data-count="3" data-include="Kids,Teens,Child"></div>`
  - Flourishing page: `<div data-apat-events="grid" data-count="3" data-include="Flourishing"></div>`
- `embeds/` is the older version (kept until nothing on the site uses it).
