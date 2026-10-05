# Qyvaria OS

> **“An operating system for AI.”**

Qyvaria OS is an independent, browser-native AI operating system and software ecosystem built from the kernel outward. Instead of treating AI as an add-on, extension, or cloud-hosted web app inside a conventional browser, Qyvaria inverts the relationship—integrating AI tooling, runtime management, and modular workspace navigation straight into the core shell.

---

## 📋 Table of Contents
1. [Core Architecture: Three Concentric Layers](#core-architecture-three-concentric-layers)
2. [Included Components & Features](#included-components--features)
   - [Qyvaria Browser](#qyvaria-browser)
   - [Qyvaria Com (AI BIOS)](#qyvaria-com-ai-bios)
   - [QyChat](#qychat)
   - [Qyvaria Python Kernel (qyvaria.py)](#qyvaria-python-kernel-qyvariapy)
3. [Local AI Integration & Architecture](#local-ai-integration--architecture)
4. [UI / UX Design & Features](#ui--ux-design--features)
5. [Installer & Deployment Features](#installer--deployment-features)
6. [Repository Structure](#repository-structure)
7. [Current Status & Roadmap](#current-status--roadmap)
8. [License & Credits](#license--credits)

---

## Core Architecture: Three Concentric Layers

Qyvaria is organized into three sequential trust and execution layers:

1. **Layer 1 — The Kernel (`qyvaria.py`)**  
   A single-file Python kernel bundle acting as the local runtime bridge, carrying command parsers, deterministic permission gates, execution pipelines, model bridging support, and system heartbeats.

2. **Layer 2 — Qyvaria AI Software**  
   The practical surface converting raw dispatch capabilities into actionable work, including multi-agent orchestration concepts, workflow definitions, prompt generation tools, and research modules.

3. **Layer 3 — Qyvaria OS**  
   The browser-native operating environment shell providing custom protocol pages (`qyvaria://`), workspace management, local vault integration, and native command routing.

---

## Included Components & Features

### 🌐 Qyvaria Browser
The main operating shell and browser workspace serving as the core foundation for Qyvaria OS.

* **Multi-tab workspace:** Seamlessly manage multiple tabs and projects concurrently.
* **Integrated AI modules:** Direct access to AI-powered features directly inside the shell.
* **Custom `qyvaria://` protocol pages:** Dedicated internal pages tailored specifically for OS management.
* **Vault / workspace management:** Secure and organized file/vault tracking.
* **Native QyChat panel:** Quick access to the assistant environment.
* **Sidebar tool system:** Modular tool access right from the edge of your screen.
* **Browser-native command routing:** Fluid execution of internal commands without heavy network overhead.
* **Internal module launcher:** Easily launch and switch between installed sub-modules.
* **AI-integrated workflow environment:** Built from the ground up to assist with daily tech workflows.

### 🧠 Qyvaria Com (AI BIOS)
An integrated AI operating layer running natively inside Qyvaria OS (`qyvaria://com`).

* **Real-time AI workspace:** Live execution and interaction zone.
* **AI BIOS control system:** Deep-level control and monitoring of internal AI parameters.
* **Agent orchestration:** Coordinate multi-agent tasks and behaviors.
* **Neural map visualization:** Visual graphs and representations of agent/neural activity.
* **Tool execution framework:** Run local and system-level tools securely.
* **Knowledge-base infrastructure:** Store and query local knowledge directly.
* **Local-first AI runtime:** Complete autonomy without mandatory cloud connectivity.
* **Voice / chat integration:** Interact naturally via text or voice.
* **AI avatar system:** Visual companion/avatar presence.
* **Runtime telemetry and logs:** Live diagnostics, debugging, and system telemetry feeds.

### 💬 QyChat
An integrated assistant environment for handling direct queries and complex workspace directives.

* **Local model routing:** Intelligently route tasks to the best local model.
* **Chat interface:** Clean, modern conversational workspace.
* **Context-aware workspace integration:** Understands what you are working on across tabs and vaults.
* **Tool invocation:** Executes commands and triggers modules on demand.
* **Kernel bridge communication:** Direct pipeline to `qyvaria.py`.
* **Voice-ready architecture:** Prepared for real-time speech integration.

### 🐍 Qyvaria Python Kernel (`qyvaria.py`)
The core local runtime bridge driving the backend operations.

* **Local execution pipeline:** Secure handling of local system routines.
* **Model bridge support:** Seamless translation between Qyvaria components and local runtimes like Ollama.
* **Runtime orchestration:** Manages background execution queues and threads.
* **Command execution:** CLI and programmatic command parsing.
* **AI service communication:** Manages requests between UI components and local LLMs.
* **Kernel heartbeat and monitoring:** Health checks and status monitoring.
* **Modular integration support:** Easily plug in new backend extensions.

---

## Local AI Integration & Architecture

Qyvaria OS is built with a strictly **local-first, offline-capable** philosophy:

* **Supported Backends:** Primary integration with **Ollama**.
* **Model Support:** Fully compatible with **Qwen** models and other local LLMs.
* **Default Configurations:**  
  * `qwen3:14b` (Primary heavy reasoning lane)  
  * `qwen3:8b` (Fast responsive lane)  
  * Optional coder/runtime lanes.
* **Capabilities:** Offline execution workflows, native model switching, and fallback runtime handling.

---

## UI / UX Design & Features

* **Cyber/neural UI design:** Futuristic, dark-mode-first aesthetic with glowing accents and clean borders.
* **Dynamic workspace layouts:** Flexible window and panel arrangements.
* **Right-side module rail:** Fast access to widgets, tools, and system controls.
* **Interactive vault system:** Visual data organization.
* **Animated AI visualization:** Live graphical representations of neural and agent processing.
* **Real-time telemetry panels:** Keep track of resource consumption and system status.
* **Fullscreen operating mode:** Immersive OS experience.
* **Desktop-native styling:** Mimics a true desktop environment inside a browser-native shell.
* **Integrated command systems & floating QyChat controls:** Access chat and commands from anywhere instantly.

---

## Installer & Deployment Features

The Windows setup package includes everything needed out of the box:

* One-file installer executable (`.exe`)
* Automatic desktop shortcut generation
* Start Menu integration
* App icon installation & setup icon integration
* Auto-folder provisioning
* Integrated software deployment & native Qyvaria Com registration
* Embedded software payloads

---

## Repository Structure

Included repository materials and directories:

* `qyvaria.py` — Core single-file Python kernel bridge
* `Qyvaria OS installer builds/` — Windows executable setup packages
* `Qyvaria Browser assets/` — Main shell and workspace graphic/UI assets
* `Qyvaria Com integration modules/` — AI BIOS backend and frontend modules
* `Documentation/` — Architecture notes and technical manuals
* `Licensing/` — LICENSE and NOTICE files
* `UI assets/` — Icons, themes, and design tokens
* `Runtime configuration files/` — Default JSON/YAML configurations for models and kernels

---

## Current Status & Roadmap

* **Release Channel:** Public Alpha
* **Version:** v1.0.0
* **Status:** Functional, experimental, actively evolving, and intended for iterative expansion.

### Planned Future Areas:
* Native desktop runtime packaging
* Expanded kernel orchestration & plugin marketplace
* Advanced agent systems & distributed AI execution
* Native voice runtime & multi-model pipelines
* Persistent neural workspace memory & real-time collaboration
* Security sandboxing & native executable packaging

---

## License & Credits

* **License:** Licensed under the **Apache License 2.0**. See the [LICENSE](LICENSE) and [NOTICE](NOTICE) files for full licensing and attribution information.
* **Credits:** Created by Jan Havlasek (Havlasek1John) / Qyvaria project.
* **Powered by:** Python, Browser-native architecture, Local AI infrastructure, Open-source AI ecosystems, Ollama, Qwen models, and custom Qyvaria runtime systems.

---

> **Important Notice:** This software is provided for research, experimentation, development, and AI workspace exploration purposes. Future releases may introduce breaking changes, architecture modifications, expanded runtime systems, and new module frameworks.
