# Banana Hub config backups

Public JSON snapshots live at `backups/<game.GameId>.json`. Bot source is maintained privately.

Packages contain schemaVersion, gameId, placeId, placeVersion and data. Readers require an exact game/place/version match. Automatic publication requires three matching network votes under the configured consensus policy. Player IDs and HWIDs are client claims; different IPs do not authenticate different people.

RideAPet v5443 is available at `backups/10035204815.json` (14 config tables). The owner explicitly requested this first publication during a live client demonstration on 2026-10-13 UTC: real captured config data, three simulated client identities, and one backup commit after the settling period. This demonstrates the upload pipeline; it is not evidence of three independent contributors. Production voter state and proxy policy were unchanged.
