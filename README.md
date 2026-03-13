# Pi-hole Controller

Control and monitor your [Pi-hole v6](https://pi-hole.net/) directly from your Elgato Stream Deck.

---

## Features

| Button | Description |
|--------|-------------|
| **Enable Blocking** | Re-enable Pi-hole DNS blocking |
| **Disable Blocking** | Disable Pi-hole DNS blocking |
| **Timed Disable** | Disable blocking for a set duration with a live countdown |
| **Status Indicator** | Shows blocking state — green (active), red (disabled), yellow (unreachable) |
| **Stats Display** | Displays a single live metric — configured per button in the Property Inspector. Available metrics: Total Queries, Queries Blocked, % Blocked, Domains on List, Q/min, Load (1/5/15m), Memory, Active Clients, Total Clients |
| **Version Info** | Shows current Pi-hole version; highlights when an update is available |
| **Open Pi-hole UI** | Opens the Pi-hole admin interface in your browser |

---

## Requirements

- Elgato Stream Deck software 6.9 or later
- Windows 10+ or macOS 13+
- Pi-hole v6 or later
- A Pi-hole **App Password** (Settings → API → App Passwords in the Pi-hole admin UI)

---

## Installation

Install from the [Elgato Marketplace](#) *(link coming soon)*.

---

Pi-hole Controller brings your Pi-hole dashboard to your Stream Deck. Stop opening a browser just to pause blocking or check your stats — do it with a button press.

**Control blocking instantly**
Enable or disable Pi-hole DNS blocking with a single key. Need a temporary pause? Use the Timed Disable button — set a duration, press it, and a live countdown shows exactly how long until protection resumes.

**Live stats, always visible**
Add as many Stats Display buttons as you want, each showing a different metric updated in real time:
- Total Queries
- Queries Blocked
- Percentage Blocked
- Domains on Blocklist
- Queries per Minute
- System Load (1 / 5 / 15 min)
- Memory Usage
- Active Clients / Total Clients

Each metric has its own color-coded icon so you can identify buttons at a glance.

**Status at a glance**
The Status Indicator button shows your Pi-hole's current state in color: green when blocking is active, red when disabled, and yellow when the device can't be reached.

**Version tracking**
The Version button shows your current Pi-hole version and highlights when an update is available — no need to log into the admin UI to check.

**Open Pi-hole UI**
One button to open your Pi-hole admin interface directly in your browser.

---

## Setup

1. Install **Pi-hole Controller** from the Elgato Marketplace.
2. In your Pi-hole admin UI, go to **Settings → API → App Passwords** and create a new App Password.
3. Add any Pi-hole Controller button to your Stream Deck profile.
4. In the Property Inspector (right panel), enter:
   - **Host** — your Pi-hole's IP address or hostname (e.g. `pi.hole` or `192.168.1.2`)
   - **Port** — typically `80`, or `443` if using HTTPS
   - **App Password** — the password you just created
5. Click **Test Connection** to confirm everything is working.
6. All buttons share the same connection — you only need to configure it once.

> **Using HTTPS?** Check the HTTPS box and the port will update to 443 automatically. Works with reverse proxies (Nginx, Caddy, etc.).

---

## Configuration

1. Add any plugin button to your Stream Deck profile.
2. In the Property Inspector, enter your Pi-hole host, port, and App Password.
3. Click **Test Connection** to verify.
4. All buttons on the deck share the same connection settings.

---

## Reporting Issues

Found a bug or have a feature request? Please [open an issue](../../issues/new/choose) and fill out the relevant template.

Before submitting:
- Check the [existing issues](../../issues) to avoid duplicates.
- Include your Pi-hole version and Stream Deck software version.
