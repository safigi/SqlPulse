# Privacy Policy

**Last updated: March 2026**

SqlPulse is a local SSMS extension. It has no accounts, no cloud sync, and no telemetry by default.

---

## Data stored locally

All data SqlPulse creates stays on your machine under `%LOCALAPPDATA%\SqlPulseTool\`:

| File | Contents | Sensitive? |
|------|----------|------------|
| `history.jsonl` | Query text, timestamp, connection info | Yes — contains your SQL queries |
| `settings.json` | Extension configuration and license token | Low — no credentials |
| `extension.log` | Diagnostic log with `[Tag]` prefixes | Low — no query content by default |
| `db-groups.json` | Database group definitions | Low |
| `job-groups.json` | Job group definitions | Low |

**SqlPulse never reads or transmits the contents of your query history, result grids, or connection strings.**

---

## Data sent over the network

### License activation (Pro only)

A one-time HTTPS POST is sent to the SqlPulse activation server containing:

- Your **license key** (the key you purchased from LemonSqueezy)
- A **machine fingerprint**: `SHA-256(UUID + CPU ID + Disk Serial)`, truncated to 32 hex characters. This is a one-way hash — the raw hardware identifiers are never sent.
- An **isVm** flag (true/false)

Nothing else is sent. No username, no hostname, no IP address is stored. After activation the signed token is stored locally and verified offline on every startup.

> **Note:** The activation server is not yet deployed. Pro license activation is not live in the current release.

### Renewal

When a token approaches expiry (within 14 days), the extension sends the existing token and fingerprint to the renewal endpoint to obtain a fresh token. Same data as activation — no additional fields.

### Telemetry / usage analytics

**Disabled by default.** If you enable "Track feature usage" in Settings > Advanced, only anonymous feature counts are stored locally (e.g. `filter: 12`, `export_csv: 5`). This data is never uploaded anywhere.

---

## SQL Server History Backend (Pro)

If you configure the SQL Server History Backend, query history is written to a SQL Server table **you specify**. SqlPulse connects using the connection string you provide — it does not control or have access to that server independently.

---

## Data retention

SqlPulse does not impose retention limits. History grows until you clear it manually (Settings > History > Clear History) or configure a max-entry limit.

---

## Children's privacy

SqlPulse is a developer tool not intended for use by anyone under 16.

---

## Changes to this policy

Updates will be reflected in this file in the [SqlPulse documentation repository](https://github.com/IstvanSafar/SqlPulse). The "Last updated" date at the top will change.

---

## Contact

For privacy questions or data requests: open an issue at [GitHub Issues](https://github.com/IstvanSafar/SqlPulse/issues).
