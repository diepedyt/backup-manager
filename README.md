# Banana Hub config backups

Public JSON snapshots live at `backups/<placeId>/<placeVersion>.json`. Bot source is maintained privately.

Each place has an `index.json` listing saved versions in ascending order and `latestVersion`. Clients select their exact running place version when available, otherwise the newest saved version below it. They never load a future-version snapshot. For example, a client on 1544 uses 1543 if no 1544 snapshot exists.

Packages contain schemaVersion, gameId, placeId, placeVersion and data. Clients perform one check per eligible execution, comparing actual config values with the selected backup. A version bump with unchanged data sends nothing. Different data is submitted directly through the configured Discord webhook, without an added startup delay or polling loop.

The bot automatically publishes after three matching packages with distinct claimed user IDs and HWIDs and a 30-second settling period. It independently compares config data again; an unchanged package creates no new version file. Changed data and the version index are published together in one Git commit. Version files are immutable and older uploads cannot move the latest default backwards.

There is no separate upload receiver. These identity claims can be forged; Discord does not expose sender IPs. The owner explicitly accepted this policy. Submitted JSON is inert data.

RideAPet v5443 is available at [backups/124216119978534/5443.json](backups/124216119978534/5443.json), with 14 config tables. Its [version index](backups/124216119978534/index.json) controls default lookup. The old `backups/10035204815.json` seed remains for older loaders; new publications use the place/version directory.

The owner explicitly requested the first publication during a live client demonstration on 2026-10-13 UTC: real captured config data, three simulated client identities, and one backup commit after the settling period. This demonstrates the upload pipeline, not three independent contributors. Migration preserves that captured data and its provenance.
