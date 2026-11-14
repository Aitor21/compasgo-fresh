# Compasgo freshness data

What has changed on the ground since each country's places were published in
[Compasgo](https://compasgo.com), the offline trip planner: places that closed
for good, places that may have closed, and places whose opening hours changed.

Written every night by a bot that reads the OpenStreetMap change files
[Geofabrik](https://download.geofabrik.de) publishes for each country. Nobody
edits these files by hand.

## Layout

    places/<CC>/fresh.json

    {
      "version": 1,
      "country": "SI",
      "through": "2026-11-13T21:22:20Z",          last change file read
      "closed": { "<place id>": { "since": "2026-10-18", "why": ["osm:lifecycle"] } },
      "unsure": { "<place id>": { "since": "...", "why": ["osm:deleted"] } },
      "hours":  { "<place id>": { "openFromMin": 630, "lastEntryMin": 1080,
                                  "closedDays": ["Sa", "Su"], "since": "..." } }
    }

`closed` places are no longer offered for new plans. `unsure` places are kept,
with a "check before you go". `hours` replace the published opening window, in
minutes after midnight.

## Licence

Derived from OpenStreetMap data, © OpenStreetMap contributors, available under
the [Open Database License](https://opendatacommons.org/licenses/odbl/1-0/).
This derived database is available under the same licence.
