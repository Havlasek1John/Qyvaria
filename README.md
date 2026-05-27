<!--
Qyvaria public GitHub README
Repository: Havlasek1John/Qyvaria
Author: Jan Havlasek
SPDX-License-Identifier: Apache-2.0
-->

# Qyvaria

**Qyvaria OS · Qyvaria AI Software · `qyvaria.py` Python Kernel · Multi-Agent AI Engineering Runtime**

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](LICENSE)
[![Python](https://img.shields.io/badge/Python-qyvaria.py-3776AB.svg)](qyvaria.py)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)](#qyvaria-os-desktop-packages)
[![Status](https://img.shields.io/badge/Status-Public%20Open%20Source-success.svg)](#license)
[![Project](https://img.shields.io/badge/Project-Qyvaria-6f42c1.svg)](#what-is-qyvaria)

**Qyvaria** is an open-source AI engineering project created by **Jan Havlasek**.

This repository is the public home for **Qyvaria OS**, **Qyvaria AI Software**, and the **`qyvaria.py` single-file Python kernel bundle**. Qyvaria is a long-running, continuously evolving software and research effort focused on prompt generation, AI-engine orchestration, multi-agent simulation, research tooling, voice/runtime experiments, local AI workflows, and public documentation.

> Qyvaria OS, Qyvaria AI Software, and the `qyvaria.py` kernel corpus are released under the **Apache License 2.0**, unless a specific file, package, bundled dependency, or third-party component states otherwise.

---

## Important links

| Resource | Link | Purpose |
|---|---|---|
| **Qyvaria Forums** | https://qyvaria.boards.net/ | Feedback, questions, community discussion, user support, and public suggestions. |
| **Qyvaria Software Wikipedia / Index** | https://qyvaria-ai-studio-index.vercel.app/ | Public Qyvaria software index, wiki-style reference, and navigation hub. |
| **GitHub Repository** | https://github.com/Havlasek1John/Qyvaria | Source code, public files, releases, issues, and project history. |

Feedback is welcome. Please use the **Qyvaria Forums** for discussions, ideas, testing notes, user reports, and community feedback: https://qyvaria.boards.net/

---

## Repository description for GitHub About panel

Use this as the short GitHub repository description:

```text
Qyvaria OS and Qyvaria AI Software: Apache-2.0 open-source AI engineering software, experimental Qyvaria OS materials, and the qyvaria.py single-file AI bundle by Jan Havlasek.
```

Suggested GitHub topics:

```text
qyvaria, qyvaria-os, ai-software, ai-kernel, prompt-engineering, agent-simulation, multi-agent, python, electron, react, apache-2-0, open-source
```

---

## What is Qyvaria?

Qyvaria is a public AI software project built around a single-file Python kernel called **`qyvaria.py`** and a wider Qyvaria OS software ecosystem.

Qyvaria is intended to be:

- a public software home for Qyvaria OS and Qyvaria AI Software,
- a single-file Python AI engineering bundle,
- a prompt-generation and AI-engine orchestration kernel,
- a multi-agent simulation and testing environment,
- a research and experimentation surface,
- a documentation and release platform,
- a long-term evolving project that keeps growing through testing, feedback, and iteration.

The project is experimental and evolving. Some parts are polished and ready for public use, some parts are research-oriented, and some parts are early-stage. The goal is to keep the work open, inspectable, documented, and organized so that people can understand it, test it, improve it, and build on it.

---

## A living project notice

Qyvaria is not a frozen one-time upload. It is a continuing life-work project.

The project has been worked on for a long time and is expected to keep evolving. New versions, new documents, new modules, new package formats, new Qyvaria OS integrations, and new public explanations may appear over time. The repository should therefore be read as a living public development record, not as a final static product.

The public release philosophy is:

- publish what can be shared,
- keep attribution clear,
- credit people and open-source software,
- document what is known,
- label what is experimental,
- accept feedback,
- improve through testing,
- keep evolving.

If you have feedback, bug reports, documentation notes, feature ideas, testing results, or suggestions, please use the Qyvaria Forums:

https://qyvaria.boards.net/

---

## Qyvaria software wiki and public index

The public Qyvaria software wiki / index is here:

https://qyvaria-ai-studio-index.vercel.app/

Use it as a navigation point for Qyvaria software information, public documentation, index pages, explanations, project context, and future Qyvaria reference material.

This GitHub repository is the software/source/release home. The Qyvaria software wiki / index is the public reading and navigation layer.

---

## Core project parts

| Area | Purpose |
|---|---|
| **Qyvaria OS** | Public desktop package materials and experimental AI workspace for Windows and Linux. |
| **Qyvaria AI Software** | AI engineering utilities, local workflows, prompt tools, documentation, and public release materials. |
| **`qyvaria.py`** | Single-file Python Qyvaria kernel corpus and runtime bundle. |
| **Prompt generator** | Structured prompt generation for SDXL, Midjourney, Flux, and generic engines. |
| **Agent modules** | Multi-agent simulation, model testing, optimization, memory, voice, research, and orchestration components. |
| **Documentation library** | Public manuals, audits, architecture notes, release plans, and project explanations. |
| **Repository governance** | License, security, contribution, support, notices, changelog, citation, and credits files. |
| **Community feedback** | Forum-based discussion and public support through Qyvaria Forums. |

Current inspected public package version:

```text
Qyvaria OS 1.0.63.6
```

---

## What `qyvaria.py` is

`qyvaria.py` is the public single-file Python kernel bundle for Qyvaria. It is intended to act as a portable software corpus and runtime wrapper containing Qyvaria-related modules, prompt tooling, agent concepts, and local AI engineering utilities.

In simple terms, `qyvaria.py` is a compact single-file package that can be moved, inspected, executed, and published as one Python artifact.

The kernel can be used for prompt generation and Qyvaria-compatible command flows.

### Basic command

```bash
python qyvaria.py --subject "futuristic tram in Prague" --style cinematic --engine sdxl -n 4
```

### Deterministic example

```bash
python qyvaria.py --subject "isometric eco-city block" --style pixel --engine generic -n 4 --seed 42
```

### Default Qyvaria command pattern

```bash
python qyvaria.py --subject "{subject}" --style cinematic --engine sdxl -n 4
```

### Expanded Qyvaria command pattern

```bash
python qyvaria.py --subject "{subject}" --style {style} --engine {engine} -n {count} --seed {seed}
```

---

## Supported prompt engine modes

```text
sdxl
midjourney
flux
generic
```

---

## Supported prompt fields

Qyvaria prompt output is organized around structured fields:

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

---

## Common style packs

Common Qyvaria style packs include:

```text
cinematic
photoreal
product
interior
architecture
food
macro
watercolor
anime
pixel
vector
diagram
clay
ui
blueprint
```

---

## Qyvaria OS desktop packages

Qyvaria OS desktop packages are intended for Windows and Linux release distribution.

Large operating-system packages should be uploaded as **GitHub Release assets**, not committed directly into the normal repository root.

Recommended release files:

| File | Platform | Purpose |
|---|---:|---|
| `Qyvaria_OS_Windows.zip` | Windows | Qyvaria OS Windows package. |
| `Qyvaria_OS_Linux.zip` | Linux | Qyvaria OS Linux package. |
| `qyvaria.py` | Cross-platform | Single-file Qyvaria Python kernel bundle. |

The repository itself should stay focused on source, documentation, setup files, and governance files.

---

## Qyvaria OS quick start

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

## Suggested GitHub setup

For a clean public GitHub repository:

1. Keep the main repository root small and readable.
2. Keep `README.md`, `LICENSE`, `NOTICE`, `CREDITS.md`, `SECURITY.md`, `CONTRIBUTING.md`, and `qyvaria.py` in the repository root.
3. Put large Windows and Linux desktop ZIP packages in **GitHub Releases**.
4. Put large PDFs, books, and historical archives in Releases or a `docs/` folder only when they are intentionally part of the public source tree.
5. Keep third-party credits and open-source acknowledgements in `THIRD_PARTY_NOTICES.md`.
6. Use the Qyvaria Forums for public discussion and community feedback.

---

## What belongs in GitHub Releases?

Use GitHub Releases for files that are meant to be downloaded as finished release assets.

Examples:

```text
Qyvaria_OS_Windows.zip
Qyvaria_OS_Linux.zip
Qyvaria_Master_Publication_Book.pdf
large audit PDFs
large documentation archives
packaged binaries
```

The repository root should not become a storage folder for every large binary. Releases are cleaner for users and easier to maintain.

---

## Credits and acknowledgements

### Creator and maintainer

**Jan Havlasek**  
Creator of Qyvaria OS, Qyvaria AI Software, and the `qyvaria.py` kernel corpus.

### Special thanks

**Jiri Burda** is credited for inspiration, motivation, testing, training, and support given in regard to Qyvaria.

This support is recognized as part of the human context around the project: testing, encouragement, motivation, feedback, training effort, and personal support that helped Qyvaria continue evolving.

### Open-source software credit

Qyvaria exists inside a much larger open-source world. The project gives thanks and credit to the open-source communities, maintainers, contributors, documentation writers, package authors, standards authors, and public software projects that make work like Qyvaria possible.

This includes, where applicable, ecosystems and tools such as:

- Python and the Python standard library,
- Apache-licensed open-source software,
- Git and GitHub,
- Node.js and npm,
- Electron,
- React,
- Vite,
- JavaScript and TypeScript tooling,
- FastAPI and related Python web tooling,
- NumPy, pandas, scikit-learn, Pillow, and optional scientific Python tools,
- PyTorch and optional AI/ML libraries,
- open documentation tools,
- open web standards,
- public developer communities,
- public tutorials, examples, and shared engineering knowledge.

Third-party dependencies remain under their own licenses. See [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md) when present.

### Public support

Thanks to the public, users, testers, readers, open-source communities, and everyone who gives constructive feedback, encouragement, bug reports, ideas, and support.

Qyvaria is better when people test it, question it, improve it, and discuss it openly.

---

## Open-source notice

Qyvaria source code is released under Apache-2.0 unless a specific file states otherwise.

Third-party software, dependencies, optional packages, frameworks, runtime tools, and bundled components remain under their own licenses. This repository attempts to respect those licenses through attribution, notices, and separation of Qyvaria source from external dependencies.

If a third-party notice is missing or incomplete, please report it through the Qyvaria Forums or GitHub Issues so it can be corrected.

---

## Safety and security

Do not upload:

- API keys,
- tokens,
- private keys,
- passwords,
- private user data,
- proprietary datasets,
- non-public model credentials,
- private system prompts,
- private logs,
- private customer data,
- confidential files.

Security-sensitive reports should be sent privately to the maintainer instead of being posted in public GitHub issues.

Qyvaria is experimental software. Do not use it as a security-critical, medical, legal, financial, emergency, or safety-critical system without independent review, testing, and validation.

---

## Experimental status

Qyvaria is a public evolving software project. The repository may include:

- stable public documentation,
- working prompt-generation commands,
- experimental runtime modules,
- local OS package materials,
- research prototypes,
- partially implemented ideas,
- historical project files,
- release candidates,
- future-facing architecture notes.

Public release does not mean every subsystem is production-certified. The goal is to keep improving the project with clear documentation, open feedback, release notes, and responsible public structure.

---

## Testing and feedback

Feedback is important to Qyvaria.

Please report:

- installation issues,
- command-line problems,
- broken documentation,
- confusing README sections,
- dependency problems,
- missing credits,
- missing third-party notices,
- ideas for better examples,
- feature requests,
- Qyvaria OS package feedback,
- `qyvaria.py` prompt-generation feedback.

Preferred community feedback location:

https://qyvaria.boards.net/

GitHub Issues may also be used for repository-specific bugs or documentation changes.

---

## Contribution guidelines

Contributions are welcome when they preserve:

- public safety,
- project attribution,
- Apache-2.0 license structure,
- third-party license respect,
- clear documentation,
- no-secrets policy,
- small reviewable changes,
- honest labeling of experimental features.

Please read:

- [`CONTRIBUTING.md`](CONTRIBUTING.md)
- [`SECURITY.md`](SECURITY.md)
- [`CODE_OF_CONDUCT.md`](CODE_OF_CONDUCT.md)
- [`CREDITS.md`](CREDITS.md)
- [`THIRD_PARTY_NOTICES.md`](THIRD_PARTY_NOTICES.md)

---

## Roadmap

Qyvaria is expected to keep evolving. Possible roadmap areas include:

- cleaner GitHub repository structure,
- improved documentation,
- better Qyvaria OS release packaging,
- clearer `qyvaria.py` command examples,
- more reproducible tests,
- stronger checksum and release verification,
- clearer third-party dependency notices,
- public wiki expansion,
- public forum support,
- better examples for SDXL, Midjourney, Flux, and generic prompt engines,
- improved issue templates and release notes,
- better distinction between stable features and experimental research modules.

---

## Checksums

Current uploaded package checksums may include:

```text
qyvaria.py                 SHA256 8fbe528dfe604d6cdc7223caae364dca8c029b3e317dd3d8721f0dab0d027ad8
Qyvaria_OS_Linux.zip       SHA256 1c615659dec5463a67e8acf561a1460cfc083fa97ff1f8ca3baf1bafecc3551e
Qyvaria_OS_Windows.zip     SHA256 519233fbaad9bb29e424d7c7983365afff90b2befda8a8ef9025b569dc4502da
```

Always regenerate checksums when files are replaced.

---

## Citation

If you reference Qyvaria in public documentation, research notes, videos, posts, or derivative projects, please cite the repository and credit **Jan Havlasek** as the creator.

Suggested citation:

```text
Jan Havlasek, Qyvaria OS and Qyvaria AI Software, public open-source AI engineering project, Apache-2.0, https://github.com/Havlasek1John/Qyvaria
```

---

## License

**Primary project license:** Apache License 2.0  
**Author:** Jan Havlasek  
**SPDX identifier:** `Apache-2.0`

See [`LICENSE`](LICENSE) for the full license text.

---

## Maintainer

**Jan Havlasek**  
Project: **Qyvaria OS / Qyvaria AI Software / `qyvaria.py` kernel corpus**  
License: **Apache-2.0**

Qyvaria keeps evolving.
