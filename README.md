<!--
Qyvaria public GitHub landing file.
Save this exact file as: README.md
Repository: Havlasek1John/Qyvaria
Author: Jan Havlasek
SPDX-License-Identifier: Apache-2.0
-->

# Qyvaria OS

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-qyvaria.py-3776AB.svg)](qyvaria.py)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)](#downloads)
[![Status](https://img.shields.io/badge/Status-Public%20Open%20Source-success.svg)](#license)

**Qyvaria OS** and **Qyvaria AI Software** are open-source AI engineering tools by **Jan Havlasek**.

This repository publishes the **Qyvaria OS desktop packages** and the **`qyvaria.py` kernel corpus**: a single-file Python AI bundle for prompt generation, AI-engine orchestration, agent simulation, research tooling, voice/runtime experiments, and local Qyvaria workflows.

> Public license declaration: Qyvaria OS, Qyvaria AI Software, and the `qyvaria.py` kernel corpus are released under the **Apache License 2.0**, unless a file or bundled third-party dependency states otherwise.

---

## GitHub repository description

Use this in the GitHub **About** panel:

```text
Qyvaria OS and Qyvaria AI Software: an Apache-2.0 open-source AI engineering OS, prompt/orchestration kernel, and qyvaria.py corpus by Jan Havlasek.
```

Suggested GitHub topics:

```text
qyvaria, qyvaria-os, ai-software, ai-kernel, prompt-engineering, agent-simulation, python, electron, react, apache-2-0, open-source
```

---

## What is included

| Area | Purpose |
|---|---|
| **Qyvaria OS** | Desktop AI workspace for Windows and Linux. |
| **Qyvaria AI Software** | AI engineering utilities, local workflows, prompt tools, and agent modules. |
| **`qyvaria.py`** | Single-file Qyvaria kernel corpus and runtime bundle. |
| **Prompt generator** | Generates structured prompts for SDXL, Midjourney, Flux, and generic engines. |
| **Agent modules** | Multi-agent simulation, model testing, optimization, voice, memory, research, and orchestration components. |
| **QyPilot / QyResearch / QyCode / QEngineer** | Qyvaria OS workspace modules included in the OS packages. |

Current inspected OS package version:

```text
Qyvaria OS 1.0.63.6
Qyvaria OS V63.6 adds QyPilot browser access across the one-toolbar, dashboard, sidebar, and options menu.
```

---

## Downloads

Use GitHub **Releases** for binary packages and keep the root repository clean.

Recommended release assets:

| File | Platform | Purpose |
|---|---:|---|
| `Qyvaria OS (Windows).zip` | Windows | Compact Windows setup package. |
| `Qyvaria OS (Linux).zip` | Linux | Compact Linux setup package. |
| `qyvaria.py` | Cross-platform | Single-file Qyvaria kernel corpus. |

The compact OS packages restore Electron/npm dependencies on first run when needed, so internet access may be required during initial setup.

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

### Linux

```bash
unzip "Qyvaria OS (Linux).zip"
cd "Qyvaria OS (Linux)"
chmod +x SETUP_QYVARIA_OS_LINUX.sh
./SETUP_QYVARIA_OS_LINUX.sh
```

### Windows

```bat
unzip "Qyvaria OS (Windows).zip"
cd "Qyvaria OS (Windows)"
SETUP_QYVARIA_OS_WINDOWS.cmd
```

Windows may need **Node.js 20+** and npm installed before first launch. Linux setup attempts to install common Electron prerequisites when a supported package manager is available.

---

## Qyvaria prompt engine

Default command pattern:

```bash
python qyvaria.py --subject "{subject}" --style cinematic --engine sdxl -n 4
```

Expanded command pattern:

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

Common style packs include:

```text
cinematic, photoreal, product, interior, architecture, food, macro,
watercolor, anime, pixel, vector, diagram, clay, ui, blueprint
```

---

## Repository layout recommendation

```text
Qyvaria/
├─ README.md
├─ LICENSE
├─ NOTICE
├─ qyvaria.py
├─ releases/
│  ├─ Qyvaria OS (Windows).zip
│  └─ Qyvaria OS (Linux).zip
└─ docs/
   ├─ SECURITY.md
   ├─ CONTRIBUTING.md
   └─ THIRD_PARTY_NOTICES.md
```

For GitHub public display, this file should be named **`README.md`** and placed in the repository root.

---

## License

**Primary project license:** Apache License 2.0  
**Author:** Jan Havlasek  
**SPDX identifier:** `Apache-2.0`

Copyright notice:

```text
Copyright 2025 Jan Havlasek

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this project except in compliance with the License.
You may obtain a copy of the License at:

    https://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.
```

Keep a separate root `LICENSE` file containing the full Apache-2.0 license text so GitHub can detect the repository license automatically.

---

## Third-party notices

Qyvaria OS packages may include or restore third-party dependencies such as Electron, React, React DOM, Vite, npm packages, Python packages, and optional AI/ML libraries. Those components remain under their own licenses.

Recommended public rule:

```text
Qyvaria source is Apache-2.0. Bundled third-party dependencies keep their original licenses. See package metadata, npm package licenses, Python package metadata, and THIRD_PARTY_NOTICES when present.
```

---

## Security and safety

Do not upload private keys, API tokens, personal data, model secrets, or proprietary datasets to the public repository.

For security reports, use a private channel instead of opening a public issue. Recommended `SECURITY.md` summary:

```text
Please report security-sensitive issues privately to the maintainer. Do not post secrets, exploit details, private keys, or personal data in public GitHub issues.
```

---

## Contributing

Contributions are welcome when they preserve the project license, attribution, safety boundaries, and public-source structure.

Recommended contribution checklist:

- Keep Qyvaria OS and `qyvaria.py` attribution to **Jan Havlasek**.
- Preserve the Apache-2.0 license notice.
- Do not add secrets or private data.
- Document new dependencies.
- Prefer small, reviewable pull requests.
- Test startup on the platform affected by the change.

---

## Release checklist

Before publishing a GitHub release:

- [ ] Root `README.md` is updated.
- [ ] Root `LICENSE` is Apache-2.0.
- [ ] `qyvaria.py` is included.
- [ ] Windows ZIP is attached to GitHub Releases.
- [ ] Linux ZIP is attached to GitHub Releases.
- [ ] Checksums are posted in the release notes.
- [ ] Third-party notices are reviewed.
- [ ] No secrets, keys, tokens, or private user data are included.

---

## Current package checksums

These checksums identify the current prepared upload set:

```text
Qyvaria OS (Linux).zip      9.41 MB      SHA256 1c615659dec5463a67e8acf561a1460cfc083fa97ff1f8ca3baf1bafecc3551e
Qyvaria OS (Windows).zip    9.41 MB      SHA256 519233fbaad9bb29e424d7c7983365afff90b2befda8a8ef9025b569dc4502da
qyvaria.py                       4.41 MB       SHA256 8fbe528dfe604d6cdc7223caae364dca8c029b3e317dd3d8721f0dab0d027ad8
```

---

## Maintainer

**Jan Havlasek**  
Project: **Qyvaria OS / Qyvaria AI Software / qyvaria.py kernel corpus**  
License: **Apache-2.0**
