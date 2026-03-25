# Changelog

All notable changes to this project will be documented in this file.

---

## [1.0.4.0] - 2026-03-24

### Fixed
- Fixed stale session being reloaded from storage after a 401 response, which caused a second Pi-hole session to be created instead of cleanly replacing the old one

---

## [1.0.3.0] - 2026-03-22

### Changed
- Pi-hole session is now persisted across plugin restarts — reuses existing session instead of creating a new one each time Stream Deck restarts
- HTTP requests now identify as `streamdeck-pihole/1.0` instead of the generic `node` or `undici` user agent

### Fixed
- Session is now properly cleaned up on logout and when connection settings are changed via Test Connection

---

## [1.0.2.0] - 2026-03-22

### Added
- Version button now refreshes immediately when pressed — no longer need to wait up to 1 hour for the next automatic check

### Fixed
- Version button no longer shows `ERR` on transient network errors — retains last known version instead

---

## [1.0.1.0] - 2026-03-21

### Fixed
- Fixed plugin crashing every ~30 minutes due to unhandled promise rejections in action callbacks (this was also causing Pi-hole to accumulate a new auth session on every crash/restart)
- Added error boundaries to all poller callbacks (status, stats, timed disable)
- Fixed first poll not forwarding errors to subscribers
- Fixed potential crash on malformed Pi-hole API responses (CPU load array access)
- Fixed partial update failures in version-info action
- Fixed Open Pi-hole UI button not handling key press errors

### Changed
- "Disable for X Seconds" button renamed to "Disable for X"

---

## [1.0.0.0] - 2026-03-19

### Added
- Enable / Disable blocking buttons
- Timed disable with live countdown ("Disable for X")
- Status indicator with color-coded state (green/red/yellow)
- Stats display with 11 selectable metrics: Total Queries, Queries Blocked, % Blocked, Domains on List, Queries/min, Load 1m/5m/15m, Memory, Active Clients, Total Clients
- Pi-hole version button with update available indicator — press to refresh immediately
- Open Pi-hole UI button
- Dynamic per-metric icons with color-coded backgrounds
- HTTPS and self-signed certificate support (compatible with reverse proxies)
- Pi-hole v6 App Password authentication
- Ignore SSL Errors option for home lab / self-signed certificate setups
