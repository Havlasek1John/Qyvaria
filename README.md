# Qyvaria

**Qyvaria OS · Qyvaria Python Kernel · AI Simulation Runtime · Multi-Agent Engineering System**

Qyvaria is an open-source AI engineering project created by **Jan/John Havlasek**.

It is a Python-based AI ecosystem built around a standalone kernel, modular agent simulations, reasoning tools, prompt-generation utilities, documentation, release materials, and Qyvaria OS public project structure. Qyvaria is not only a single script, not only a website, and not only an installer. It is a growing AI software environment designed for experimentation, inspection, research, local development, AI simulation, and future expansion.

Qyvaria brings together ideas from artificial intelligence, operating-system thinking, agent simulation, human-centered design, local-first tooling, prompt engineering, evaluation, safety policy, and open-source release practice.

The long-term goal is simple:

> Build an AI system that people can inspect, run, improve, extend, and understand.

---

## Credits

### Creator, founder, and main developer

**Jan/John Havlasek**

Qyvaria was created, designed, developed, organized, and publicly released by Jan/John Havlasek. The project vision, repository structure, Qyvaria OS direction, Python kernel packaging, public release effort, documentation direction, and core identity of Qyvaria come from his work and long-term motivation to build a stronger, more open, more human-focused AI system.

### Special credit and inspiration

**Jiří Burda**

Special credit goes to **Jiří Burda** for innovational ideals, inspiration, motivation, support, feedback, model-training direction, and encouragement during the development of Qyvaria. His influence helped shape the spirit, ambition, and direction of the project.

Qyvaria exists not only because of code, but because of ideas, persistence, support, experimentation, learning, and belief in what AI systems can become when they are built with purpose.

---

## What is Qyvaria?

Qyvaria is a modular AI project centered around the `qyvaria.py` Python kernel.

The project is designed as a single public home for:

- Qyvaria OS materials;
- the Qyvaria Python kernel;
- AI simulation modules;
- multi-agent experiments;
- reasoning and planning systems;
- prompt-generation tools;
- language and voice experiments;
- evaluation utilities;
- documentation;
- release files;
- safety and policy drafts;
- website/public project materials;
- future Qyvaria-compatible tools.

Qyvaria can be studied as a software bundle, used as an experimental AI runtime, extended as a development platform, or treated as a foundation for future Qyvaria OS and Qyvaria Studio work.

The project is still growing. Some parts are polished, some are experimental, and some are early research ideas. That is intentional. Qyvaria is meant to evolve in public.

---

## Why Qyvaria exists

Modern AI tools are often closed, hidden, remote, or hard to inspect. Qyvaria was created with a different direction.

Qyvaria should be:

- open enough to study;
- local enough to inspect;
- modular enough to extend;
- ambitious enough to grow;
- safe enough to use responsibly;
- documented enough for other people to understand;
- powerful enough to support real AI experimentation.

The purpose of Qyvaria is not only to generate answers. The purpose is to create an environment where AI components can cooperate, reason, simulate, evaluate, and improve.

A strong AI system should not be only a black box. It should have visible structure. It should have a kernel. It should have release files. It should have safety policies. It should have credits. It should have documentation. It should have a path for contributors. It should have a vision.

Qyvaria is an attempt to build that path.

---

## Project philosophy

Qyvaria is built on several important ideas.

### 1. AI should be inspectable

Users and developers should be able to see what is inside the system. Qyvaria uses a standalone Python bundle so people can run, list, extract, inspect, and study the internal files.

### 2. AI should be modular

A serious AI system is not one function. It is many components working together: reasoning, memory, tools, agents, evaluation, planning, safety, language, voice, data, and interface layers.

### 3. AI should stay human-centered

Qyvaria is built to help people. It should support human creativity, decision-making, engineering, learning, and research. It should not remove human responsibility.

### 4. Simulation matters

Before an AI system acts, it should be able to simulate, reason, evaluate, compare, and check. Qyvaria includes simulation-oriented modules because simulation is one of the foundations of safer and smarter AI.

### 5. Open-source discipline matters

A real project needs more than code. It needs a license, notices, contribution rules, security reporting, release notes, checksums, documentation, and public accountability.

### 6. Motivation matters

Qyvaria is also a project of persistence. It exists because of work, support, ideas, inspiration, feedback, and belief in future AI systems. That is why credit is part of the README, not an afterthought.

---

## Main repository file

The most important file is:

```text
qyvaria.py
```

This is the Qyvaria Python kernel bundle.

It acts as a self-contained source package and runtime entrypoint. It can show bundle statistics, list bundled files, extract internal files, write an internal README, and run the configured Qyvaria entrypoint.

This makes Qyvaria easier to share, archive, inspect, and run from one primary Python file.

---

## Quick start

Clone the repository:

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
```

Check Python:

```bash
python --version
```

Show help:

```bash
python qyvaria.py --help
```

Show bundle statistics:

```bash
python qyvaria.py --stats
```

List files inside the bundle:

```bash
python qyvaria.py --list
```

Extract the internal source files:

```bash
python qyvaria.py --extract extracted_qyvaria
```

Write the internal bundle README:

```bash
python qyvaria.py --readme BUNDLE_README.md
```

Run the configured Qyvaria entrypoint:

```bash
python qyvaria.py --run
```

---

## Command reference

The standalone Qyvaria bundle supports commands like:

```bash
python qyvaria.py [--stats] [--list] [--extract DIR] [--readme [PATH]] [--run]
```

### `--stats`

Prints metadata and summary information about the bundle.

Example:

```bash
python qyvaria.py --stats
```

Use this first when you want to understand the bundle.

### `--list`

Lists files embedded inside the Qyvaria bundle.

Example:

```bash
python qyvaria.py --list
```

This is useful for seeing what modules and assets are included.

### `--extract DIR`

Extracts the embedded bundle contents into a directory.

Example:

```bash
python qyvaria.py --extract qyvaria_extracted
```

After extraction, you can inspect the modules as normal files.

### `--readme [PATH]`

Writes the internal bundle README.

Example:

```bash
python qyvaria.py --readme
```

or:

```bash
python qyvaria.py --readme docs/BUNDLE_README.md
```

### `--run`

Runs the configured Qyvaria entrypoint.

Example:

```bash
python qyvaria.py --run
```

---

## Recommended first workflow

For a new user or developer, the best first workflow is:

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
python qyvaria.py --help
python qyvaria.py --stats
python qyvaria.py --list
python qyvaria.py --extract extracted_qyvaria
```

Then inspect the extracted directory.

On macOS or Linux:

```bash
find extracted_qyvaria -maxdepth 3 -type f
```

On Windows PowerShell:

```powershell
Get-ChildItem -Recurse extracted_qyvaria | Select-Object FullName
```

---

## Qyvaria OS

Qyvaria OS is the operating-environment identity of the project.

It represents the idea that Qyvaria is more than a library. It is a full AI-oriented software environment that can grow into a system with its own structure, tools, interface, release package, installer assets, documentation, and runtime direction.

Qyvaria OS should be understood as:

- an AI operating-environment concept;
- a public release package direction;
- a home for Qyvaria tools and runtime components;
- a future-facing identity for the ecosystem;
- an open-source base that can be improved over time.

Qyvaria OS is not trying to replace traditional operating systems like Windows, Linux, or macOS. Instead, it is an AI system layer and project identity built on top of existing platforms.

---

## Qyvaria Python Kernel

The Qyvaria Python kernel is the heart of this repository.

The kernel gives Qyvaria a portable structure. It allows a large project to be carried inside a single Python file while still preserving internal modules and metadata.

The kernel approach helps with:

- portability;
- inspection;
- archiving;
- reproducibility;
- public release packaging;
- single-file distribution;
- extraction into normal source files;
- future bootstrapping of Qyvaria tools.

The kernel is designed so that a user can start with one file, understand what is inside, then extract and inspect the project deeper.

---

## Multi-agent simulation

Qyvaria includes AI simulation and multi-agent design ideas.

A multi-agent system is a system where different agents or modules can have different responsibilities. One module might plan. Another might critique. Another might evaluate. Another might analyze data. Another might manage memory. Another might check safety.

This architecture is important because real AI systems should not rely on only one response path. They should be able to compare, test, reflect, and correct.

Possible agent roles in a Qyvaria-style system include:

- planner agent;
- critic agent;
- code analysis agent;
- language agent;
- safety agent;
- memory agent;
- evaluator agent;
- voice agent;
- prompt-generation agent;
- data-analysis agent;
- simulation agent;
- tool-routing agent.

Qyvaria is a foundation for experimenting with these patterns.

---

## Prompt engineering and creative AI tools

Qyvaria includes prompt-generation and creative workflow ideas.

Prompt engineering is not only writing a sentence. A strong prompt can include:

- subject;
- environment;
- style;
- mood;
- camera direction;
- composition;
- lighting;
- materials;
- color palette;
- scale;
- post-processing;
- negative prompt terms;
- target engine parameters.

Qyvaria can support structured prompt generation for different engines and styles. This makes it useful for creative AI workflows, image-generation experiments, design exploration, and visual prototyping.

---

## Reasoning and evaluation

Qyvaria is not only about producing output. It is also about checking output.

AI systems need evaluation because generated answers can be wrong, incomplete, biased, unsafe, or low quality. A stronger system should be able to test, compare, score, and improve its outputs.

Qyvaria’s direction includes:

- reasoning loops;
- self-evaluation;
- comparison tools;
- output scoring;
- memory-aware analysis;
- code review support;
- data review support;
- prompt testing;
- model-behavior experiments;
- quality-control utilities.

The goal is to make AI behavior more understandable and improvable.

---

## Language and communication

Qyvaria is designed with language as a core part of the system.

Language is more than text. It includes meaning, tone, culture, translation, speech, conversation, emotion, structure, and context.

Qyvaria can grow toward supporting:

- multilingual reasoning;
- Czech and English project identity;
- translation tools;
- linguistic analysis;
- voice conversation;
- structured dialogue;
- human-friendly explanations;
- documentation generation;
- communication agents.

The project should remain open to people from different languages and backgrounds.

---

## Voice and interface direction

Qyvaria includes the idea of voice-enabled AI interaction and future interface layers.

Voice matters because many users do not want to interact with AI only through code or text boxes. A future Qyvaria interface could support spoken interaction, assistant-style workflows, local voice tools, and real-time command routing.

Voice features may require optional dependencies or external services depending on implementation. Users should review each module before enabling voice or network-connected functionality.

---

## Safety and responsibility

Qyvaria should be used responsibly.

Do not use Qyvaria to harm people, steal information, bypass security, impersonate others, spread deception, automate abuse, create malware, or make high-impact decisions without human review.

AI systems can make mistakes. They can produce false information. They can misunderstand context. They can reflect problems in their data or design. Qyvaria should be treated as a tool that requires human judgment.

Responsible use includes:

- reviewing important outputs;
- testing before deployment;
- keeping humans in control;
- protecting private data;
- avoiding harmful automation;
- documenting limitations;
- using sandboxed environments;
- checking security-sensitive code;
- respecting laws and platform rules.

Qyvaria is powerful because it is open and flexible. That also means users and contributors must act responsibly.

---

## Privacy

Do not put private data into public commits.

Do not commit:

- API keys;
- passwords;
- tokens;
- private `.env` files;
- private user data;
- personal documents;
- secret model keys;
- private server credentials;
- private Cloudinary/API configuration;
- production database credentials.

If you build with Qyvaria, document what your extension stores, where it stores it, and whether it sends data to an external service.

Local-first design is preferred whenever possible.

---

## Security

Security reports are welcome.

Please report security issues privately instead of opening a public issue when the vulnerability could put users at risk.

Security contact:

```text
Qyvaria1ai@gmail.com
```

When reporting a vulnerability, include:

- affected file or module;
- description of the issue;
- steps to reproduce;
- possible impact;
- suggested fix if known.

Security is especially important because Qyvaria may include modules related to code execution, local files, web servers, API tools, voice input, model integrations, and release packaging.

---

## Installation notes

Qyvaria can be inspected with Python and the repository files.

Some internal modules may require optional dependencies. Because Qyvaria is broad, not every module should be expected to run in a minimal Python environment without installing additional packages.

Recommended setup:

```bash
python -m venv .venv
```

Activate the environment.

Windows:

```bash
.venv\Scripts\activate
```

macOS / Linux:

```bash
source .venv/bin/activate
```

Then run:

```bash
python qyvaria.py --help
python qyvaria.py --stats
```

Install extra packages only when you know which module needs them.

---

## Development workflow

A safe development workflow is:

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
python -m venv .venv
```

Activate the virtual environment.

Then inspect the bundle:

```bash
python qyvaria.py --stats
python qyvaria.py --list
python qyvaria.py --extract extracted_qyvaria
```

Before running an extracted module:

1. Read the file.
2. Check imports.
3. Check file access.
4. Check network access.
5. Check whether it starts a server.
6. Check whether it executes commands.
7. Check whether it needs API keys.
8. Run only inside a safe environment.

---

## Repository structure

The repository may include files such as:

```text
Qyvaria/
├─ README.md
├─ LICENSE
├─ NOTICE
├─ CONTRIBUTING.md
├─ SECURITY.md
├─ CODE_OF_CONDUCT.md
├─ TRADEMARKS.md
├─ THIRD_PARTY_NOTICES_DRAFT.md
├─ qyvaria.py
├─ docs/
├─ site/
├─ public/
└─ releases/
```

The exact structure may change as the project grows.

---

## License

Qyvaria is released under the license provided in this repository.

If this repository contains the Apache License 2.0, then Qyvaria may be used, modified, distributed, and built upon under the terms of Apache-2.0.

Always read the actual license file:

```text
LICENSE
```

Also read:

```text
NOTICE
```

This README is only a project explanation. The license file controls the legal terms.

---

## Trademarks and project identity

The Qyvaria name, Qyvaria OS identity, logos, icons, and related branding belong to the Qyvaria project identity.

You may fork and modify the source under the project license, but do not use the Qyvaria name in a misleading way.

Good examples:

```text
Built with Qyvaria.
```

```text
Based on Qyvaria by Jan/John Havlasek.
```

Bad examples:

```text
Official Qyvaria release
```

when the release is not actually official.

See `TRADEMARKS.md` if included.

---

## Contributing

Contributions are welcome when they improve the project clearly and responsibly.

Good contributions include:

- better documentation;
- bug fixes;
- examples;
- tests;
- safer defaults;
- cleaner module structure;
- dependency cleanup;
- release verification;
- packaging improvements;
- security hardening;
- translations;
- architecture diagrams;
- website improvements;
- accessibility improvements.

Before contributing, please read:

```text
CONTRIBUTING.md
CODE_OF_CONDUCT.md
SECURITY.md
```

A good pull request should explain:

- what changed;
- why it changed;
- how it was tested;
- whether dependencies changed;
- whether there are risks;
- whether documentation needs updates.

---

## Future goals

Qyvaria can grow in many directions.

Important future goals include:

### 1. Cleaner dependency groups

Separate dependencies into groups such as:

- core;
- developer;
- web;
- voice;
- image;
- machine learning;
- data analysis;
- optional integrations.

### 2. More examples

Add examples that users can run quickly after cloning the repository.

### 3. More tests

Add tests for core bundle behavior, extraction, module loading, utility functions, and safety checks.

### 4. Better architecture documentation

Add diagrams explaining how Qyvaria OS, the Python kernel, agents, memory, policy, tools, and interface layers relate.

### 5. Stable and experimental labels

Clearly mark which modules are stable, experimental, research-only, deprecated, or planned.

### 6. Release verification

Make checksums, manifests, release notes, and installer verification easy to find and understand.

### 7. Better website integration

Improve public website files so they clearly explain Qyvaria while linking back to the source, license, security policy, and release materials.

### 8. More human-centered AI behavior

Continue developing Qyvaria toward AI that is useful, honest, explainable, careful, and aligned with human responsibility.

---

## Frequently asked questions

### Is Qyvaria only one Python file?

No. The main public kernel is `qyvaria.py`, but that file can contain and expose many internal modules. The repository also includes documentation, release materials, policy files, and public project structure.

### Is Qyvaria a library?

Partly. It can be treated like a Python-based AI bundle, but it is broader than a normal library. It is also a runtime experiment, OS-style project, documentation set, and public AI engineering environment.

### Is Qyvaria OS a normal operating system?

Qyvaria OS is an AI operating-environment identity and project direction. It is not meant to replace Windows, Linux, or macOS. It is a layer and ecosystem for AI tools, agents, and runtime ideas.

### Can I fork Qyvaria?

Yes, according to the repository license terms.

### Can I use Qyvaria commercially?

Check the license file. If the repository is under Apache-2.0, commercial use is generally allowed under the Apache-2.0 terms.

### Is everything production-ready?

No. Qyvaria includes experimental modules. Review, test, and verify before serious use.

### Does Qyvaria need internet access?

Basic inspection does not require internet access. Some optional modules may use APIs, models, web tools, or external services. Review each module before running it.

### Where should I start?

Start here:

```bash
python qyvaria.py --help
python qyvaria.py --stats
python qyvaria.py --list
python qyvaria.py --extract extracted_qyvaria
```

---

## Recommended safety checklist before running modules

Before running unfamiliar code from the extracted bundle:

- use a virtual environment;
- avoid running as administrator/root;
- check imports;
- check network calls;
- check file writes;
- check subprocess usage;
- check API-key usage;
- check external dependencies;
- check whether the module starts a server;
- review outputs before trusting them.

This is a good habit for any broad AI engineering project.

---

## Contact

Creator, founder, and main developer:

```text
Jan/John Havlasek
```

Special credit:

```text
Jiří Burda
```

Project email:

```text
Qyvaria1ai@gmail.com
```

Main repository:

```text
https://github.com/Havlasek1John/Qyvaria
```

Qyvaria OS repository:

```text
https://github.com/Havlasek1John/Qyvaria-OS-
```

---

## Acknowledgements

Qyvaria is credited first to **Jan/John Havlasek**, the creator, founder, and main developer of the project.

Special thanks and credit go to **Jiří Burda** for innovational ideals, inspiration, motivation, support, feedback, training direction, and encouragement connected to the development and growth of Qyvaria.

This project is also dedicated to the idea that AI should be built with courage, responsibility, imagination, and human purpose.

---

## Final note

Qyvaria is more than a file.

It is a project, a kernel, a runtime idea, an OS direction, a simulation environment, a public release, and a long-term vision for human-centered AI.

Use it carefully. Study it deeply. Improve it responsibly. Build with it creatively.

**Qyvaria by Jan/John Havlasek.  
With special credit to Jiří Burda for inspiration, support, motivation, innovational ideals, and model-development guidance.**
