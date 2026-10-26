# DeckerGUI — Demo (Windows x64)

![platform](https://img.shields.io/badge/platform-Windows%20x64-0078D6?logo=windows&logoColor=white)
![edition](https://img.shields.io/badge/edition-demo-ff8c00)
![version](https://img.shields.io/badge/version-1.12.0-1f6feb)
![TypeScript](https://img.shields.io/badge/TypeScript-5.9-3178C6?logo=typescript&logoColor=white)
![Node.js](https://img.shields.io/badge/Node.js-%E2%89%A522-339933?logo=node.js&logoColor=white)
![license](https://img.shields.io/badge/license-Proprietary-red)
![owner](https://img.shields.io/badge/owner-Wan%20Mohd%20Azizi%20bin%20Wan%20Hosen-0A66C2)
![publisher](https://img.shields.io/badge/publisher-CTECX%20Agentic%20Engineering%20Technologies%20%26%20Services%20PLT-6A5ACD)
[![Sponsor](https://img.shields.io/badge/sponsor-ctaxnagomi-EA4AAA?logo=githubsponsors&logoColor=white)](https://github.com/sponsors/ctaxnagomi)

A runnable **Windows x64 demo** of the DeckerGUI ecosystem console.

> **Binaries only.** This repository intentionally ships **no source code**. It
> contains the compiled demo client and nothing else.

## What this is

The demo exposes only the **end-to-end path** of the DeckerGUI CLI:

`dock` · `hubnet` · `persona` · `afm` · `status`

Every other command is refused with a notice. `--version` reads
`1.12.0 (Demo version)`.

The client runs a **Docking Station** on the device, connects it to a
DeckerGUI hub/emitter, and drives a **persona → AFM job → approved → artifact**
flow.

## Download

Grab **`DGUI-Client-win-x64.zip`** from this repository, then extract it to a
folder such as `C:\DGUI-Client`.

## What's inside

| File | Purpose |
| --- | --- |
| `deckerGUI.exe` | The demo CLI (Node SEA single-file executable, demo edition) |
| `dock.cjs` | The bundled Docking Station (no repo or `npm install` needed) |
| `sandboxRunner.mjs` | The compiled-workload sandbox used by the dock |
| `setup.cmd` | One-time configuration (points this device at a peer hub) |
| `dock-up.cmd` | Starts the dock |

## Requirements

- Windows 10/11 **x64**
- **Node.js 22 or newer on `PATH`** — the demo executable bundles its own Node
  runtime, but `dock up` launches the docking station with the system `node`.
  Verify with `node -v`.
- Network access to your DeckerGUI hub/emitter host (LAN or tunnel).

## Quick start

```bat
:: 1. extract the zip, then:
cd C:\DGUI-Client

:: 2. one-time setup — point this device at your hub/emitter (default 192.168.0.5)
setup.cmd <PEER_IP>

:: 3. start the dock
dock-up.cmd

:: 4. verify
deckerGUI.exe --version
deckerGUI.exe dock status
```

The vendor inbox is then reachable at `http://<this-device>:3198/`.

## Demo scope

| Allowed | Everything else |
| --- | --- |
| `status`, `dock`, `hubnet`, `persona`, `afm` | refused (demo notice) |

## Owner & Publisher

- **Owner:** Wan Mohd Aziz bin Wan Hosen ([@ctaxnagomi](https://github.com/ctaxnagomi)) — ctaxnagomi@deckergui.my
- **Publisher:** CTECX Agentic Engineering Technologies & Services PLT — ctecx_dgui@deckergui.my
- **Sponsor:** [GitHub Sponsors](https://github.com/sponsors/ctaxnagomi)



© 2026 Wan Mohd Aziz bin Wan Hosen. Published by CTECX Agentic Engineering Technologies & Services PLT. All rights reserved.

## License

**Proprietary.** See [LICENSE](LICENSE). This repository distributes compiled
demo artifacts only; no source, no right to reverse-engineer, modify, or
redistribute.
