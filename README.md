# gbfr-logs

[![GitHub Release](https://img.shields.io/github/v/release/false-spring/gbfr-logs)](https://github.com/false-spring/gbfr-logs/releases)
[![GitHub Downloads](https://img.shields.io/github/downloads/false-spring/gbfr-logs/total)](https://github.com/false-spring/gbfr-logs/releases)
[![Discord](https://img.shields.io/discord/1218833963032776774?style=flat&label=discord&color=7289da)](https://discord.gg/GR4r9zrqJj)
[![GitHub License](https://img.shields.io/github/license/false-spring/gbfr-logs)](./LICENSE)

<a href="https://www.buymeacoffee.com/false.spring" target="_blank"><img src="https://cdn.buymeacoffee.com/buttons/default-orange.png" alt="Buy Me A Coffee" height="41" width="174"></a>

Experimental overlay DPS meter for Granblue Fantasy: Relink, based on the reverse engineering work from [naoouo/GBFR-ACT](https://github.com/nyaoouo/GBFR-ACT).

## How to install

- Go to [Releases](https://github.com/false-spring/gbfr-logs/releases)
- Download the latest .msi installer and run it.
- Open GBFR Logs after the game is already running.

## Screenshots

### DPS Overlay

![Meter](./docs/screenshots/meter.png)

### Skill Tracking

![Meter](./docs/screenshots/skill-tracking.png)

### Historical Logs

![Logs](./docs/screenshots/log-history.png)

### DPS Charts

![Charts](./docs/screenshots/charting.png)

### Sigil Tracking

![Sigil Tracking](./docs/screenshots/sigil-tracking.png)

### Multi-language Support

![Simplified Chinese](./docs/screenshots/simplified-chinese.png)

## Frequently Asked Questions

> Q: The meter isn't updating or displaying anything.

Try running the program after the game has been launched. Be sure to run the program as admin.

> Q: Is this safe? My antivirus is marking the installation as a virus / malware.

You can ignore these as false positives.

- GBFR Logs does code injection into the running game process which can look like a virus-like program.
- GBFR Logs reads game memory and initializes code hooks in order to receive damage data.
- I recommend adding an exception / whitelisting for the installation folder for the best experience, but you may not need to do so if you haven't ran into this issue.

Windows Defender: https://support.microsoft.com/en-us/windows/add-an-exclusion-to-windows-security-811816c0-4dfd-af4a-47e4-c301afe13b26

> Q: How do I update?

Same as with installing, you can download the [latest release](https://github.com/false-spring/gbfr-logs/releases) and run the installer again and it will update over your old installation.

> Q: How do I uninstall?

You can uninstall GBFR Logs the normal way through the Control Panel or by running the uninstall script in the folder where you installed it to. You may also want to remove these folders.

- `%AppData%\gbfr-logs`

> Q: My issue isn't listed here, or I have a suggestion.

Feel free to create a [new GitHub issue](https://github.com/false-spring/gbfr-logs/issues) or [join the Discord server](https://discord.gg/GR4r9zrqJj).

> Q: How do I add/edit my language?

Read [src-tauri/lang/README.md](./src-tauri/lang/README.md) for more information on how to add/edit language support!

## For Developers

- Install nightly Rust ([rustup.rs](https://rustup.rs/)) + [Node.js](https://nodejs.org/en/download).
- Install NPM dependencies with `npm install`
- `npm run tauri dev`

## Under the hood

This project is split up into a few subprojects:

- `src-hook/` - Library that is injected into the game that broadcasts essential damage events.
- `src-tauri/` - The Tauri Rust backend that communicates with the hooked process and does parsing.
- `protocol/` - Defines the message protocol used by hook + back-end.
- `src/` - The JS front-end used by the Tauri web app

## Credits

This project would not have been possible without the following folks:

- [nyaoouo/GBFR-ACT](https://github.com/nyaoouo/GBFR-ACT) for the original reverse engineering work.
- [Harkain](https://github.com/Harkains) for their work on formatting and translating skills to friendly English names.
