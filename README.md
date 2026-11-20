# sheller-timer

Timer that nudges the Sheller subscription manager's sheet-sync endpoint every 5 minutes.

- `.github/workflows/sync.yml` — every 5 minutes, POSTs to the Sheller sync-pull endpoint so new spreadsheet applications are imported automatically. It runs on GitHub Actions (public repository, free) so it keeps working independently of any local machine.
- `.github/workflows/heartbeat.yml` — once a month, updates `heartbeat.txt` with a small commit so GitHub does not disable the scheduled workflows after 60 days of repository inactivity.

No secrets are stored in this repository. The access key lives only in this repository's Actions secrets (`SHELLER_SYNC_SECRET`).
