# apat-events

A Place at the Table's events feed. Every hour, GitHub Actions reads APAT's public Church Center calendar (aptc.churchcenter.com) and registrations and publishes:

- `https://legacyco.github.io/apat-events/events.json` (read by the Squarespace embeds)
- `https://legacyco.github.io/apat-events/events.ics` (calendar people can subscribe to)
- `https://legacyco.github.io/apat-events/events.rss.xml`
- `https://legacyco.github.io/apat-events/changes.json` (what changed since the last run, plus Register link warnings)
- `https://legacyco.github.io/apat-events/preview.html` (every embed with live data)

No secrets. Only events APAT published on Church Center come through. Past events are kept back 5 years (as far as Church Center returns).

Source of truth: `church-events-sync/` in `LegacyCo/legacy_playground` (APAT's folder is `church-events-sync/clients/a-place-at-the-table/`). Change embeds there, rebuild with `build_client_embeds.py a-place-at-the-table`, and copy `embeds/` here.

If a run fails, nothing is published and the site keeps the last good list.
