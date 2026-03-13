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
