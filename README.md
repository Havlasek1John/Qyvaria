<div align="center">

# Qyvaria

**A single-file AI kernel. A solo AI engineering studio. A browser built to run AI natively.**

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](./LICENSE)
[![Kernel](https://img.shields.io/badge/Kernel-qyvaria.py-3776AB.svg)](./qyvaria.py)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)](#qyvaria-os)
[![Status](https://img.shields.io/badge/Status-Public%20%2F%20Evolving-success.svg)](#project-status)
[![Maintainer](https://img.shields.io/badge/Maintainer-Jan%20Havlasek-informational.svg)](https://github.com/Havlasek1John)

*Built and maintained solo by [Jan Havlasek](https://github.com/Havlasek1John) under Qyvaria — a donation-based AI studio.*

</div>

---

## Table of Contents

- [What is Qyvaria](#what-is-qyvaria)
- [The Kernel — `qyvaria.py`](#the-kernel--qyvariapy)
- [Qyvaria AI Software](#qyvaria-ai-software)
- [Qyvaria OS — the AI Browser](#qyvaria-os--the-ai-browser)
- [Architecture Overview](#architecture-overview)
- [Getting Started](#getting-started)
- [Repository Layout](#repository-layout)
- [Project Status](#project-status)
- [Roadmap](#roadmap)
- [Credits](#credits)
- [Contributing & Support](#contributing--support)
- [License](#license)

---

## What is Qyvaria

**Qyvaria** is an independent, solo-built AI engineering project made up of three things that fit together:

1. **A kernel** — `qyvaria.py`, a deterministic, single-file command dispatch core.
2. **AI software built on that kernel** — the tools, agents, and workflows that run through it.
3. **Qyvaria OS** — a Chromium-based browser designed to host and run that AI software natively, rather than as a website inside someone else's browser.

Qyvaria isn't a wrapper around someone else's model or a thin UI over an API. It's an attempt to build the whole stack — the dispatch core, the AI layer on top of it, and the runtime environment it lives in — as one coherent, inspectable system.

The project is run and maintained by one person, funded by donations, and developed in public.

---

## The Kernel — `qyvaria.py`

At the center of everything is **`qyvaria.py`** — a single-file Python kernel that every other Qyvaria component is built around.

The kernel is designed around a few non-negotiable principles:

| Principle | What it means in practice |
|---|---|
| **Single-file architecture** | The entire kernel lives in one Python file. No hidden logic scattered across a dozen modules — if you can open `qyvaria.py`, you can read the whole core. |
| **Deterministic behavior** | Given the same input and the same seed/state, the kernel produces the same output. No hidden randomness, no silent state mutation. |
| **RBAC-safe command dispatch** | Every command that flows through the kernel is checked against a role-based access model before it executes. Commands don't get to run just because they were typed — they get to run because they're *permitted*. |
| **Portable by design** | Because it's one file, `qyvaria.py` can be copied, inspected, versioned, and executed independently of the rest of the repository. |

The kernel has gone through several internal generations as it's evolved — internally named **Aetheris**, **Aeon**, **Cetana**, and **Varia** — each iteration refining the dispatch model, the permission system, and the runtime's determinism guarantees. What ships in this repository is the current public generation.

### Basic usage

```bash
python qyvaria.py --subject "example task" --engine generic -n 4
```

### Deterministic usage (fixed seed)

```bash
python qyvaria.py --subject "example task" --engine generic -n 4 --seed 42
```

The kernel accepts structured command patterns and dispatches them through its RBAC layer before any downstream AI software module touches them.

---

## Qyvaria AI Software

Everything built *on top of* the kernel falls under **Qyvaria AI Software** — the actual working layer a user or developer interacts with.

This includes:

- **Command-driven AI workflows** that route through `qyvaria.py`'s dispatch system
- **Multi-agent orchestration** — coordinating multiple AI roles/agents against a shared, permission-checked command surface
- **Local-first tooling** — designed to run on a user's own machine rather than depend on a hosted backend
- **Research and experimentation modules** — some stable, some explicitly labeled as in-progress

Qyvaria AI Software is intentionally kept close to the kernel: the goal is that every AI capability in the project can be traced back to a specific, auditable command passing through `qyvaria.py`, rather than opaque logic buried in application code.

---

## Qyvaria OS — the AI Browser

**Qyvaria OS** is the newest and most ambitious layer of the project: a **Chromium-based custom browser built to run Qyvaria's AI software as a native part of the browsing environment**, instead of as a tab-based web app.

Where most "AI in the browser" products are extensions or sidebars bolted onto Chrome, Qyvaria OS takes the opposite approach — it builds AI directly into the browser shell itself.

### What makes it different

- **Chromium-based foundation** — built on the same open engine as Chrome, giving it full web compatibility while allowing deep customization of the shell around it.
- **Native `chrome://qyvaria-os/` support** — through source-level patching of the Chromium build, Qyvaria OS can expose its AI tooling as a first-class internal browser page, the same way `chrome://settings` or `chrome://extensions` are native to Chrome.
- **Custom launchers** — dedicated entry points for starting Qyvaria OS and its AI runtime together, rather than launching a browser and separately starting an AI backend.
- **Local Node.js server integration** — Qyvaria OS runs a local Node.js server alongside the browser shell, acting as the bridge between the browser UI and the `qyvaria.py` kernel / AI software layer.
- **Phased toolkit development** — Qyvaria OS is being built in defined phases, with the current toolkit generation (**Phase 4**) covering the launcher system, local server integration, and the groundwork for native URL patching.

### A note on running it

Full native builds of Qyvaria OS — especially the source-patched Chromium variant — require a proper **Linux desktop environment** and non-trivial build resources (disk space, RAM, and build time). This isn't a "clone and run" browser build; it's closer to building Chromium itself with a custom layer added on top. Lighter local walkthroughs and script-level audits are available for anyone who wants to inspect the toolkit without doing a full native build.

---

## Architecture Overview

```
┌─────────────────────────────────────────────┐
│                 Qyvaria OS                   │
│   Chromium-based browser shell               │
│   • chrome://qyvaria-os/ (patched, native)   │
│   • Custom launchers                         │
│   • Local Node.js bridge server              │
└───────────────────┬───────────────────────────┘
                     │
┌────────────────────▼──────────────────────────┐
│              Qyvaria AI Software               │
│   Multi-agent workflows, orchestration,        │
│   local-first tooling, research modules        │
└────────────────────┬──────────────────────────┘
                     │
┌────────────────────▼──────────────────────────┐
│                qyvaria.py                       │
│   Single-file kernel                            │
│   • Deterministic execution                     │
│   • RBAC-safe command dispatch                  │
│   • Generations: Aetheris → Aeon → Cetana → Varia│
└─────────────────────────────────────────────────┘
```

Every layer above the kernel exists to make `qyvaria.py` more usable — the AI software gives it workflows, and Qyvaria OS gives it a native home to run in.

---

## Getting Started

### Requirements

- Python 3.x for the `qyvaria.py` kernel
- Node.js 20+ for Qyvaria OS's local bridge server (Windows builds especially)
- A Linux desktop environment for full native Qyvaria OS builds with source patching

### Run the kernel

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
python qyvaria.py --subject "your task" --engine generic -n 4
```

### Launch Qyvaria OS (packaged builds)

Packaged Qyvaria OS builds are distributed as release assets rather than committed to the repository root.

**Linux**
```bash
unzip "Qyvaria_OS_Linux.zip"
cd "Qyvaria OS (Linux)"
chmod +x SETUP_QYVARIA_OS_LINUX.sh
./SETUP_QYVARIA_OS_LINUX.sh
```

**Windows**
```bat
unzip "Qyvaria_OS_Windows.zip"
cd "Qyvaria OS (Windows)"
SETUP_QYVARIA_OS_WINDOWS.cmd
```

> Windows setups may require Node.js 20+ and npm before first launch. Linux setups may require standard Electron/Chromium build dependencies.

---

## Repository Layout

```
Qyvaria/
├─ README.md
├─ LICENSE
├─ NOTICE
├─ CREDITS.md
├─ ACKNOWLEDGEMENTS.md
├─ THIRD_PARTY_NOTICES.md
├─ SECURITY.md
├─ CONTRIBUTING.md
├─ CODE_OF_CONDUCT.md
├─ SUPPORT.md
├─ CHANGELOG.md
├─ CITATION.cff
├─ pyproject.toml
├─ requirements.txt
├─ CHECKSUMS.sha256
├─ qyvaria.py
└─ apps/qyvaria-os/         # Qyvaria OS toolkit, launchers, and browser shell materials
```

Large binaries — Qyvaria OS Windows/Linux packages, PDFs, and build archives — are published under [GitHub Releases](https://github.com/Havlasek1John/Qyvaria/releases) rather than committed to the repository root.

---

## Project Status

Qyvaria is a **living project**, not a one-time upload. Expect the kernel, the AI software layer, and Qyvaria OS to all keep evolving in place.

- ✅ Kernel (`qyvaria.py`) — public, versioned, actively maintained
- ✅ Qyvaria AI Software — public, mixed stable/experimental modules
- 🚧 Qyvaria OS — active development, Phase 4 toolkit (launchers, local server, native URL patching groundwork)

Some parts of the project are polished and ready for public use. Others are explicitly research-stage or early prototypes. The repository is meant to be read as an ongoing development record.

---

## Roadmap

- Deeper native Chromium integration for `chrome://qyvaria-os/`
- Expanded Qyvaria OS launcher and packaging system
- Additional kernel generations beyond Varia
- Stronger RBAC policy tooling and auditing for the dispatch layer
- Clearer separation between stable and experimental AI software modules
- Continued public documentation and release-note transparency

---

## Credits

**Creator and maintainer**
Jan Havlasek — creator of the `qyvaria.py` kernel, Qyvaria AI Software, and Qyvaria OS.

**Special thanks**
Jiri Burda, for testing, motivation, and support throughout the project's development.

**Open source**
Qyvaria is built on top of, and grateful to, the broader open-source ecosystem — including Python, Node.js, Chromium, Electron, and the many tools and communities that make independent software like this possible. See [`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md) for full attribution.

---

## Contributing & Support

Contributions, bug reports, and feedback are welcome as long as they preserve the project's Apache-2.0 licensing, attribution, and no-secrets policy (no API keys, tokens, or private data in issues or PRs).

- Community discussion: [Qyvaria Forums](https://qyvaria.boards.net/)
- Public index / wiki: [Qyvaria Software Index](https://qyvaria-ai-studio-index.vercel.app/)
- Repository-specific bugs and docs: [GitHub Issues](https://github.com/Havlasek1John/Qyvaria/issues)

Please read [`CONTRIBUTING.md`](./CONTRIBUTING.md), [`SECURITY.md`](./SECURITY.md), and [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md) before opening a pull request.

---

## License

Released under the **Apache License 2.0**.
See [`LICENSE`](./LICENSE) for full terms.

```
Jan Havlasek, Qyvaria — Kernel, AI Software, and Qyvaria OS
Apache-2.0, https://github.com/Havlasek1John/Qyvaria
```

---

<div align="center">

**Qyvaria keeps evolving.**

</div>
