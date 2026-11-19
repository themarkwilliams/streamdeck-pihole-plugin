# Changelog

All notable changes to this project will be documented in this file.

---

## [1.0.7.0] - 2026-11-18

### Fixed
- Test Connection now shows Pi-hole's own reason when it can't log in, instead of only `HTTP 401: Unauthorized`
- HTTPS with **Ignore SSL Errors** now reuses one connection instead of opening a new one on every refresh
- Test Connection no longer leaves the previous Pi-hole session open. Each click used to add another session, and enough of them could fill Pi-hole's session limit

### Changed
- When Pi-hole says the password is incorrect, the property inspector shows the app password steps, including the easy-to-miss **Enable new app password** → **Save & Apply**
- If you used the main web password with 2FA turned on, Test Connection says so and suggests an app password (app passwords don't need a 2FA code)
- If something other than Pi-hole answers on that address (for example a router or a reverse proxy login), Test Connection says it doesn't look like Pi-hole and what to check
- Network problems now say what went wrong instead of "fetch failed": connection refused, host not found, an untrusted HTTPS certificate (with a hint to turn on Ignore SSL Errors), or HTTPS not matching the port
- Security updates to bundled libraries (undici, ws, Stream Deck SDK 2.1.2)

---

## [1.0.6.0] - 2026-05-28

### Fixed
- Leading/trailing whitespace in the Host and App Password fields is now automatically trimmed — prevents 401 errors caused by accidental copy-paste spaces
- `http://` or `https://` prefix and any trailing path (e.g. `/admin`) in the Host field are now automatically stripped — pasting a full URL works correctly

### Changed
- App Password hint in the property inspector now clarifies to copy without spaces and to leave the field blank if Pi-hole has no password set

---

## [1.0.5.0] - 2026-03-26

### Fixed
- Fixed plugin creating multiple orphaned Pi-hole sessions over time
- Removed erroneous 5-minute in-memory session expiry that caused re-authentication on every period of inactivity — session now remains valid for its full Pi-hole lifetime (~30 days)
- Old session is now explicitly deleted via `DELETE /auth` before a new one is created, preventing session accumulation on Pi-hole

### Changed
- Manifest Author updated to "Marktastic"

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
