# Pi-hole Controller

Control and monitor your [Pi-hole v6](https://pi-hole.net/) directly from your Elgato Stream Deck.

---

## Features

| Button | Description |
|--------|-------------|
| **Enable Blocking** | Re-enable Pi-hole DNS blocking |
| **Disable Blocking** | Disable Pi-hole DNS blocking |
| **Disable for X** | Disable blocking for a set duration with a live countdown |
| **Status Indicator** | Shows blocking state with color-coded icons — green (active), red (disabled), yellow (unreachable) |
| **Stats Display** | Displays a single live metric — configured per button in the Property Inspector. Available metrics: Total Queries, Queries Blocked, % Blocked, Domains on List, Q/min, Load (1/5/15m), Memory, Active Clients, Total Clients |
| **Version Info** | Shows current Pi-hole version; highlights when an update is available. Press the button to refresh immediately |
| **Open Pi-hole UI** | Opens the Pi-hole admin interface in your browser |

---

## Requirements

- Elgato Stream Deck software 6.9 or later
- Windows 10+ or macOS 13+
- Pi-hole v6 or later
- A Pi-hole **App Password** (Settings → Web interface / API, Expert mode → Configure app password, then **Enable new app password** and **Save & Apply**). Leave the App Password field blank if your Pi-hole has no password set.

---

## Installation

Install from the [Elgato Marketplace](https://marketplace.elgato.com/product/pi-hole-controller-adc5d34c-67c8-4838-abb4-2489c225ce15).

---

## Setup

1. Install **Pi-hole Controller** from the Elgato Marketplace.
2. In your Pi-hole admin UI, go to **Settings → Web interface / API**, switch to **Expert** mode and click **Configure app password**. Copy the new password, then click **Enable new app password** and **Save & Apply**: the password doesn't work until you do. Making a new app password replaces the old one. If your Pi-hole has no password set, skip this step and leave the App Password field blank.
3. Add any Pi-hole Controller button to your Stream Deck profile.
4. In the Property Inspector (right panel), enter:
   - **Host** — your Pi-hole's IP address or hostname (e.g. `pi.hole` or `192.168.1.2`)
   - **Port** — typically `80`, or `443` if using HTTPS
   - **App Password** — the password you just created
5. Click **Test Connection** to confirm everything is working.
6. All buttons share the same connection — you only need to configure it once.

> **Using HTTPS?** Check the HTTPS box and the port will update to 443 automatically. Works with reverse proxies (Nginx, Caddy, etc.).

> **Self-signed certificate?** Check **Ignore SSL Errors** to bypass certificate validation — useful for home lab setups with a local CA or self-signed cert.

### If Test Connection fails

- **"Pi-hole says the password is incorrect"**: the app password was never applied (click **Enable new app password**, then **Save & Apply**), it was replaced by a newer one, or it picked up extra characters when pasted. If your Pi-hole has no password, leave the field blank.
- **"Pi-hole wants a 2FA code"**: that's your main web password with two-factor login turned on. Use an app password instead; it doesn't need a 2FA code.
- **"This doesn't look like Pi-hole's API"**: something else answered, such as your router, a reverse proxy with its own login, or another service on that port. Check Host, Port and HTTPS.

---

## Reporting Issues

Found a bug or have a feature request? Please [open an issue](https://github.com/themarkwilliams/streamdeck-pihole-plugin/issues/new/choose) and fill out the relevant template.

Before submitting:
- Check the [existing issues](https://github.com/themarkwilliams/streamdeck-pihole-plugin/issues) to avoid duplicates.
- Include your Pi-hole version and Stream Deck software version.
