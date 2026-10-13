# Banana Hub config backups

Public JSON snapshots live at `backups/<game.GameId>.json`. Bot source is maintained privately.

Packages contain schemaVersion, gameId, placeId, placeVersion and data. Readers require an exact game/place/version match. Clients submit JSON attachments directly through the configured Discord webhook. The bot automatically publishes after three matching packages with distinct claimed user IDs and HWIDs and a 30-second settling period. There is no separate upload receiver. These claims can be forged; Discord does not expose sender IPs. The owner explicitly accepted this policy.

RideAPet v5443 is available at `backups/10035204815.json` (14 config tables). The owner explicitly requested this first publication during a live client demonstration on 2026-10-13 UTC: real captured config data, three simulated client identities, and one backup commit after the settling period. This demonstrates the upload pipeline; it is not evidence of three independent contributors. That initial demonstration preserved the then-current production voter state and proxy policy. The current webhook-only policy is described above.
