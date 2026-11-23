# Changelog

All notable changes to XLink are listed here. Versions follow [Semantic Versioning](https://semver.org/): a major release can change how XLink behaves or stores data, a minor release adds features, and a patch release fixes bugs.

## [1.1.0] - 2026-11-23

### Added
- **Install update** downloads a new release, checks its signature and installs it, in place of opening the download page.
- Monthly data cap in Settings, with a notification at 80% and 100% of it, and how much of it you've used on Trends & Usage.
- Daily speed test at an hour you choose, run by the Starlink router.
- 30-day latency, throughput and power history on Trends & Usage. XLink now keeps 90 days of hourly averages, built from your existing history on first start.

### Changed
- Packet loss counts as an interruption only after it stays above your threshold for 15 seconds, timed from when it began. Single noisy readings no longer cause a "Connection problem" and "Connection restored" notification pair.
- Outage History shows and searches every recorded interruption, not only the latest 500.
- Readings no longer resend the sky map and outage history every few seconds when they haven't changed, and the window no longer redraws everything once a second.
- When the background helper keeps failing to start, XLink waits longer between attempts (up to five minutes) instead of retrying every few seconds.

### Fixed
- The 30-day data use chart no longer runs past the edge of the window when some days have no data.

## [1.0.0] - 2026-11-15

First public release.

### Added
- Overview with live status, speeds, latency, packet loss, a live speed chart, sky map, dish health, recent interruptions and data use.
- Obstructions page: the direction the dish faces, blockage by compass direction, how often and how long blockages last, a 24-hour blockage timeline, blocked time per day, and outages caused by obstructions.
- Trends & Usage: uptime, latency, throughput and power history; data use by hour or day with per-day details.
- Network page with dish and router details, connected devices, wired port speeds, and a router speed test with a live gauge.
- Outage History with search, pages and CSV export.
- Dish settings (snow melt, sleep schedule) and dish controls with confirmation.
- Tray monitoring with a status-coloured icon and desktop notifications.
- Daily check for new XLink releases on GitHub, with a banner and a notification. Can be turned off in Settings.
- Navy night-sky theme, custom title bar and new app icon.
- The dish model, whether it has motors, and the router generation, on the Overview and Network pages.

### Fixed
- Speed test results: XLink now reads the per-second readings the Starlink router actually reports.
- The live speed test view now refreshes twice a second, as intended.
- Stow and unstow are hidden on dishes without motors (Standard, Mini), where they do nothing.
- The Obstructions page now shows how many hours of measurement its figures cover, and says when the dish doesn't report a figure instead of "None measured".

### Security
- Installers no longer contain the folder paths of the PC that built them.
- XLink starts Windows tools (`reg.exe`, `explorer.exe`) by their full system path.
- Release workflows use actions pinned to exact commits, and CI runs with a read-only token.

[1.1.0]: https://github.com/optix-thedev/xlink/releases/tag/v1.1.0
[1.0.0]: https://github.com/optix-thedev/xlink/releases/tag/v1.0.0
