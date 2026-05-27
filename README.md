<!--
Qyvaria public GitHub README
Repository: Havlasek1John/Qyvaria
Author: Jan Havlasek
SPDX-License-Identifier: Apache-2.0
-->

# Qyvaria

**Qyvaria OS · Qyvaria AI Software · qyvaria.py Python Kernel · Multi-Agent AI Engineering Runtime**

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-qyvaria.py-3776AB.svg)](qyvaria.py)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)](#downloads)
[![Status](https://img.shields.io/badge/Status-Public%20Open%20Source-success.svg)](#license)

**Qyvaria** is an open-source AI engineering project created by **Jan Havlasek**.

This repository is the public home for:

- **Qyvaria OS** public desktop package materials.
- **Qyvaria AI Software** project documentation, safety files, and release structure.
- **`qyvaria.py`**, the single-file Python kernel bundle for prompt generation, AI-engine orchestration, agent simulation, research tooling, and local AI workflows.
- Public repository governance files for license, security, contribution, support, citation, and release management.

> Qyvaria OS, Qyvaria AI Software, and the `qyvaria.py` kernel corpus are released under the **Apache License 2.0**, unless a specific file or bundled third-party dependency states otherwise.

---

## Repository description for GitHub About panel

Use this as the short GitHub repository description:

```text
Qyvaria OS and Qyvaria AI Software: Apache-2.0 open-source AI engineering software, experimental Qyvaria OS materials, and the qyvaria.py single-file AI bundle by Jan Havlasek.
```

Suggested topics:

```text
qyvaria, qyvaria-os, ai-software, ai-kernel, prompt-engineering, agent-simulation, python, electron, react, apache-2-0, open-source
```

---

## What is Qyvaria?

Qyvaria is a modular AI project centered around the **`qyvaria.py` Python kernel**. It is designed as a public home for AI software experiments, prompt-generation tools, agent simulation modules, reasoning and planning systems, local development utilities, documentation, releases, and future Qyvaria-compatible tools.

The project is experimental and evolving. Some parts are polished, some are research-oriented, and some are early-stage. The goal is to make the work inspectable, documented, and organized enough for public development.

---

## What is included?

| Area | Purpose |
|---|---|
| **Qyvaria OS** | Desktop AI workspace package materials for Windows and Linux. |
| **Qyvaria AI Software** | AI engineering utilities, local workflows, prompt tools, agent modules, and documentation. |
| **`qyvaria.py`** | Single-file Qyvaria Python kernel corpus and runtime bundle. |
| **Prompt generator** | Structured prompt generation for SDXL, Midjourney, Flux, and generic engines. |
| **Agent modules** | Multi-agent simulation, model testing, optimization, memory, voice, research, and orchestration components. |
| **Repository governance** | License, security, contribution, support, notices, release notes, and citation files. |

Current inspected public package version:

```text
Qyvaria OS 1.0.63.6
```

---

## Downloads

Large desktop packages should be published as **GitHub Release assets**, not as normal root repository files.

Recommended release assets:

| File | Platform | Purpose |
|---|---:|---|
| `Qyvaria_OS_Windows.zip` | Windows | Qyvaria OS Windows package. |
| `Qyvaria_OS_Linux.zip` | Linux | Qyvaria OS Linux package. |
| `qyvaria.py` | Cross-platform | Single-file Qyvaria Python kernel bundle. |

The main GitHub repository should stay focused on source, documentation, setup files, and governance files.

---

## Quick start

### Run the Qyvaria Python kernel

```bash
python qyvaria.py --subject "futuristic tram in Prague" --style cinematic --engine sdxl -n 4
```

Expanded deterministic example:

```bash
python qyvaria.py --subject "isometric eco-city block" --style pixel --engine generic -n 4 --seed 42
```

### Qyvaria prompt engine command pattern

```bash
python qyvaria.py --subject "{subject}" --style cinematic --engine sdxl -n 4
```

Expanded pattern:

```bash
python qyvaria.py --subject "{subject}" --style {style} --engine {engine} -n {count} --seed {seed}
```

Supported engine modes:

```text
sdxl
midjourney
flux
generic
```

Supported prompt fields:

```text
subject
style
environment
action
mood
palette
materials
camera
composition
lighting
scale
post-processing
negatives
engine
persona
seed
```

Common style packs:

```text
cinematic, photoreal, product, interior, architecture, food, macro,
watercolor, anime, pixel, vector, diagram, clay, ui, blueprint
```

---

## Qyvaria OS package quick start

### Linux

```bash
unzip "Qyvaria_OS_Linux.zip"
cd "Qyvaria OS (Linux)"
chmod +x SETUP_QYVARIA_OS_LINUX.sh
./SETUP_QYVARIA_OS_LINUX.sh
```

### Windows

```bat
unzip "Qyvaria_OS_Windows.zip"
cd "Qyvaria OS (Windows)"
SETUP_QYVARIA_OS_WINDOWS.cmd
```

Windows may require **Node.js 20+** and npm before first launch. Linux may require common Electron runtime dependencies.

---

## Recommended repository structure

```text
Qyvaria/
├─ README.md
├─ LICENSE
├─ NOTICE
├─ SECURITY.md
├─ CONTRIBUTING.md
├─ CODE_OF_CONDUCT.md
├─ SUPPORT.md
├─ CHANGELOG.md
├─ CITATION.cff
├─ pyproject.toml
├─ requirements.txt
├─ qyvaria.py
├─ docs/
├─ examples/
├─ scripts/
├─ apps/qyvaria-os/
└─ .github/
```

Recommended release-only files:

```text
release-assets/
├─ Qyvaria_OS_Windows.zip
└─ Qyvaria_OS_Linux.zip
```

---

## Checksums

Current uploaded package checksums:

```text
qyvaria.py                 SHA256 8fbe528dfe604d6cdc7223caae364dca8c029b3e317dd3d8721f0dab0d027ad8
Qyvaria_OS_Linux.zip       SHA256 1c615659dec5463a67e8acf561a1460cfc083fa97ff1f8ca3baf1bafecc3551e
Qyvaria_OS_Windows.zip     SHA256 519233fbaad9bb29e424d7c7983365afff90b2befda8a8ef9025b569dc4502da
```

---

## Security

Do not upload API keys, tokens, private keys, passwords, personal data, proprietary datasets, or non-public model credentials.

Security-sensitive reports should be sent privately to the maintainer instead of being posted in public GitHub issues.

---

## Contributing

Contributions are welcome when they preserve the project license, attribution, safety boundaries, and public-source structure.

Please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`SECURITY.md`](SECURITY.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)

---

## License

**Primary project license:** Apache License 2.0  
**Author:** Jan Havlasek  
**SPDX identifier:** `Apache-2.0`

See [`LICENSE`](LICENSE) for the full license text.

---

## Maintainer

**Jan Havlasek**  
Project: **Qyvaria OS / Qyvaria AI Software / qyvaria.py kernel corpus**  
License: **Apache-2.0**
