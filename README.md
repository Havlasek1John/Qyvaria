<div align="center">

# Qyvaria

### A Deterministic AI Kernel · A Solo AI Engineering Studio · A Browser Built to Run AI Natively

[![License: Apache-2.0](https://img.shields.io/badge/License-Apache--2.0-blue.svg)](./LICENSE)
[![Kernel](https://img.shields.io/badge/Kernel-qyvaria.py-3776AB.svg)](./qyvaria.py)
[![Platform](https://img.shields.io/badge/Platform-Windows%20%7C%20Linux-lightgrey.svg)](#7-qyvaria-os--the-ai-native-browser)
[![Status](https://img.shields.io/badge/Status-Public%20%2F%20Evolving-success.svg)](#12-project-status)
[![Maintainer](https://img.shields.io/badge/Maintainer-Jan%20Havlasek-informational.svg)](https://github.com/Havlasek1John)

*Designed, engineered, and maintained solo by [Jan Havlasek](https://github.com/Havlasek1John) — Qyvaria is a donation-supported, independent AI studio.*

</div>

---

## Table of Contents

1. [Introduction & Philosophy](#1-introduction--philosophy)
2. [System Overview](#2-system-overview)
3. [The Kernel — `qyvaria.py`](#3-the-kernel--qyvariapy)
4. [Command Lifecycle & Dispatch Pipeline](#4-command-lifecycle--dispatch-pipeline)
5. [RBAC & Security Model](#5-rbac--security-model)
6. [Kernel Generations: Aetheris → Aeon → Cetana → Varia](#6-kernel-generations-aetheris--aeon--cetana--varia)
7. [Qyvaria AI Software Layer](#7-qyvaria-ai-software-layer)
8. [Qyvaria OS — the AI-Native Browser](#8-qyvaria-os--the-ai-native-browser)
9. [Full-Stack Architecture](#9-full-stack-architecture)
10. [Installation & Usage](#10-installation--usage)
11. [Repository Layout](#11-repository-layout)
12. [Project Status](#12-project-status)
13. [Comparison: Qyvaria OS vs. Conventional AI-in-Browser Products](#13-comparison-qyvaria-os-vs-conventional-ai-in-browser-products)
14. [Roadmap](#14-roadmap)
15. [Frequently Asked Questions](#15-frequently-asked-questions)
16. [Credits](#16-credits)
17. [Contributing & Support](#17-contributing--support)
18. [License](#18-license)

---

## 1. Introduction & Philosophy

Qyvaria is an independent software project built around a simple, uncompromising idea: **an AI system should be traceable from the moment a command is issued to the moment it executes, with no unaccountable layer in between.**

Most modern "AI products" are assembled from disparate, often opaque parts — a hosted model behind an API, a UI framework glued on top, a browser extension layered over a browser that was never designed to host AI natively, and permission systems bolted on as an afterthought. Qyvaria was built to do the opposite: start from a single, auditable core, and build every other capability as a direct, traceable extension of that core.

That philosophy produces three things, developed together, in this repository:

- **A kernel** (`qyvaria.py`) — the deterministic, permission-checked core that every command in the system passes through.
- **AI Software** — the workflows, agents, and tooling that give the kernel something to do.
- **Qyvaria OS** — a Chromium-based browser purpose-built to host that AI software as a first-class citizen of the browsing environment, not a tab running inside someone else's product.

This is not a company with a roadmap dictated by investors, nor a product built to maximize engagement metrics. Qyvaria is developed by one engineer, funded by voluntary donations, and released publicly under an open license so the design decisions — good and imperfect alike — can be inspected rather than taken on faith.

> **Design mantra:** *If a command executes, you should be able to explain exactly why it was allowed to.*

---

## 2. System Overview

Qyvaria is best understood as three concentric layers, each depending on the one below it, and each adding a different kind of capability:

```mermaid
graph TD
    subgraph L3["Layer 3 — Qyvaria OS"]
        A1[Chromium-based Browser Shell]
        A2["Native chrome://qyvaria-os/ Page"]
        A3[Local Node.js Bridge Server]
        A4[Custom Launchers]
    end

    subgraph L2["Layer 2 — Qyvaria AI Software"]
        B1[Multi-Agent Orchestration]
        B2[Command-Driven Workflows]
        B3[Local-First Tooling]
        B4[Research & Experimental Modules]
    end

    subgraph L1["Layer 1 — Kernel (qyvaria.py)"]
        C1[Deterministic Execution Engine]
        C2[RBAC-Safe Command Dispatcher]
        C3[Single-File Runtime Core]
    end

    A1 --> A3
    A2 --> A3
    A4 --> A3
    A3 -->|command requests| B2
    B1 --> B2
    B2 --> C2
    B3 --> C2
    B4 --> C2
    C2 --> C1
    C1 --> C3

    style L3 fill:#1f2937,color:#fff,stroke:#4b5563
    style L2 fill:#374151,color:#fff,stroke:#6b7280
    style L1 fill:#111827,color:#fff,stroke:#374151
```

At a glance:

| Layer | Component | Primary Responsibility |
|---|---|---|
| 1 | `qyvaria.py` (Kernel) | Deterministic execution + RBAC-checked command dispatch |
| 2 | Qyvaria AI Software | Turns raw dispatch into usable AI workflows and agents |
| 3 | Qyvaria OS | Hosts the AI software natively inside a Chromium-based browser shell |

Nothing in Layer 2 or Layer 3 is permitted to bypass Layer 1. Every action — whether triggered from a terminal, a script, or a click inside Qyvaria OS — ultimately resolves to a command dispatched through the kernel.

---

## 3. The Kernel — `qyvaria.py`

At the heart of the entire project is a single Python file: **`qyvaria.py`**. This is a deliberate architectural constraint, not a limitation of scope.

### 3.1 Why single-file?

A multi-module codebase hides its true behavior across imports, indirection, and inheritance chains. A single-file kernel forces every core behavior to live in one place, in one linear read. If you can open `qyvaria.py` top to bottom, you have read the entire trust boundary of the system.

```mermaid
graph LR
    subgraph Traditional["Traditional Multi-Module Core"]
        M1[core/__init__.py] --> M2[core/dispatch.py]
        M2 --> M3[core/permissions/rbac.py]
        M3 --> M4[core/permissions/policy.py]
        M4 --> M5[core/utils/state.py]
        M5 --> M6[core/engine/executor.py]
    end

    subgraph Qyvaria["Qyvaria Kernel"]
        Q1[qyvaria.py]
    end

    style Traditional fill:#7f1d1d,color:#fff
    style Qyvaria fill:#065f46,color:#fff
```

The tradeoff is intentional: single-file design trades some conventional code organization for **total auditability**.

### 3.2 Core kernel properties

| Property | Description |
|---|---|
| **Determinism** | Given identical inputs and an identical seed/state, the kernel always produces identical output. No hidden entropy sources, no silent global-state mutation. |
| **RBAC-safe dispatch** | Every command is resolved against a role-permission table *before* it is allowed to execute — not after, not optionally. |
| **Statelessness between calls** | The kernel does not carry hidden memory between invocations unless state is explicitly passed in. |
| **Portability** | Because it is one file, `qyvaria.py` can be copied, versioned, diffed, and executed independently of the rest of the repository. |
| **Explicit failure** | Rejected commands fail loudly with an identifiable reason code, rather than failing silently or executing a "safe default" behavior. |

### 3.3 Kernel internal structure

Conceptually, the kernel is organized into four cooperating subsystems, all resident in the one file:

```mermaid
classDiagram
    class CommandParser {
        +parse(raw_input) Command
        +validate_syntax(Command) bool
    }
    class RBACGate {
        +resolve_role(context) Role
        +check_permission(Role, Command) bool
        +deny_reason(Command) str
    }
    class DeterministicExecutor {
        +execute(Command, seed) Result
        +snapshot_state() State
        +restore_state(State) void
    }
    class DispatchRouter {
        +route(Command) Handler
        +register_handler(name, Handler) void
    }

    CommandParser --> DispatchRouter : validated Command
    DispatchRouter --> RBACGate : permission check
    RBACGate --> DeterministicExecutor : approved Command
    DeterministicExecutor --> DispatchRouter : Result
```

- **CommandParser** — turns raw input (CLI args, API calls, or in-browser events from Qyvaria OS) into a structured `Command` object.
- **DispatchRouter** — decides which internal handler a command should be routed to.
- **RBACGate** — the security checkpoint every command must clear before execution.
- **DeterministicExecutor** — actually runs the approved command, with reproducibility guarantees.

### 3.4 Example invocation

```bash
python qyvaria.py --subject "example task" --engine generic -n 4
```

Deterministic (seeded) invocation, guaranteeing reproducible output across runs and machines:

```bash
python qyvaria.py --subject "example task" --engine generic -n 4 --seed 42
```

---

## 4. Command Lifecycle & Dispatch Pipeline

Every command entering the Qyvaria system — regardless of whether it originates from a terminal, a Qyvaria AI Software workflow, or a click inside Qyvaria OS — follows the same lifecycle.

```mermaid
sequenceDiagram
    autonumber
    participant U as Caller (CLI / OS / Script)
    participant P as CommandParser
    participant D as DispatchRouter
    participant R as RBACGate
    participant E as DeterministicExecutor
    participant O as Output

    U->>P: Raw command input
    P->>P: Validate syntax
    alt Invalid syntax
        P-->>U: Reject (syntax error)
    else Valid syntax
        P->>D: Structured Command object
        D->>R: Request permission check
        R->>R: Resolve caller role
        R->>R: Match role against command's required permission
        alt Permission denied
            R-->>U: Reject (RBAC denial + reason code)
        else Permission granted
            R->>E: Approved Command
            E->>E: Apply deterministic seed/state
            E->>E: Execute command logic
            E->>O: Result payload
            O-->>U: Return output
        end
    end
```

This lifecycle is identical whether the caller is a developer running `qyvaria.py` directly from a terminal, or a browser event inside Qyvaria OS being relayed through the local Node.js bridge server. **The kernel does not have a "trusted" fast path** — every caller goes through the same parser, the same RBAC gate, and the same executor.

### 4.1 Failure states are explicit

A rejected command in Qyvaria never fails silently or falls back to a default action. It returns a specific, identifiable reason:

```mermaid
flowchart TD
    Start([Command Received]) --> Syntax{Valid Syntax?}
    Syntax -- No --> RejectSyntax[["Reject: SYNTAX_ERROR"]]
    Syntax -- Yes --> Role{Role Resolved?}
    Role -- No --> RejectRole[["Reject: UNKNOWN_ROLE"]]
    Role -- Yes --> Perm{Permission Granted?}
    Perm -- No --> RejectPerm[["Reject: RBAC_DENIED"]]
    Perm -- Yes --> Exec[Execute Deterministically]
    Exec --> Result([Return Result])

    style RejectSyntax fill:#7f1d1d,color:#fff
    style RejectRole fill:#7f1d1d,color:#fff
    style RejectPerm fill:#7f1d1d,color:#fff
    style Exec fill:#065f46,color:#fff
    style Result fill:#065f46,color:#fff
```

---

## 5. RBAC & Security Model

Role-Based Access Control (RBAC) is not an add-on in Qyvaria — it is the gate every command must clear before the executor ever touches it.

### 5.1 Role hierarchy

```mermaid
graph TD
    Root[Root / Maintainer] --> Operator[Operator]
    Operator --> Agent[AI Agent Role]
    Agent --> Guest[Guest / Read-Only]

    Root -.->|full command surface| Cmds1[All Commands]
    Operator -.->|operational commands| Cmds2[Execute, Configure]
    Agent -.->|scoped AI commands| Cmds3[Query, Generate, Dispatch-Limited]
    Guest -.->|inspection only| Cmds4[Read, Inspect]

    style Root fill:#7c2d12,color:#fff
    style Operator fill:#92400e,color:#fff
    style Agent fill:#854d0e,color:#fff
    style Guest fill:#4d7c0f,color:#fff
```

| Role | Typical Caller | Command Surface |
|---|---|---|
| **Root / Maintainer** | The project maintainer, local trusted operator | Full access to all kernel commands, including configuration and permission changes |
| **Operator** | A trusted local process or script | Execute and configure operational commands, no permission-table changes |
| **AI Agent** | A Qyvaria AI Software agent or workflow | Scoped access — generate, query, and dispatch within defined boundaries |
| **Guest / Read-Only** | Qyvaria OS UI in an unauthenticated context | Inspection and read-only commands only |

### 5.2 Why RBAC lives in the kernel, not the application layer

If permission checking lived in the AI software layer or the browser shell, a bug or a malicious workflow at either of those layers could bypass it entirely. By placing RBAC inside the kernel itself — the one component every layer must route through — there is no code path in the system that reaches execution without a permission check.

```mermaid
flowchart LR
    subgraph Wrong["Permission check in application layer (avoided)"]
        W1[Browser UI] -->|bypassable| W2[AI Workflow]
        W2 -->|bypassable| W3[Permission Check]
        W3 --> W4[Kernel Execution]
        W2 -.->|shortcut possible| W4
    end

    subgraph Right["Permission check in kernel (Qyvaria design)"]
        R1[Browser UI] --> R2[AI Workflow]
        R2 --> R3[Kernel]
        R3 --> R4{RBAC Gate}
        R4 -->|only path to| R5[Execution]
    end

    style Wrong fill:#7f1d1d,color:#fff
    style Right fill:#065f46,color:#fff
```

---

## 6. Kernel Generations: Aetheris → Aeon → Cetana → Varia

The kernel did not arrive at its current form in one attempt. It has passed through four internal generations, each addressing limitations discovered in the previous one.

```mermaid
timeline
    title Kernel Generational Evolution
    Aetheris : Initial dispatch concept
             : Basic command parsing
    Aeon     : Introduced early permission checks
             : Improved state handling
    Cetana   : Refined RBAC role hierarchy
             : Stronger determinism guarantees
    Varia    : Current public generation
             : Single-file consolidation
             : Full RBAC-safe dispatch pipeline
```

| Generation | Focus | Key Advancement |
|---|---|---|
| **Aetheris** | Foundational dispatch | Established the idea of a command object and a routed handler model |
| **Aeon** | Access control groundwork | Introduced the first permission-checking logic ahead of execution |
| **Cetana** | Structural refinement | Formalized the role hierarchy and tightened determinism guarantees |
| **Varia** | Current generation | Consolidated everything into the single-file `qyvaria.py`, with the full RBAC-safe dispatch pipeline described in [Section 4](#4-command-lifecycle--dispatch-pipeline) |

Each generational name is retained internally as a versioning concept — a way of tracking *architectural* generations of the kernel, distinct from ordinary semantic version numbers.

---

## 7. Qyvaria AI Software Layer

Everything a user or developer actually *does* with Qyvaria — beyond raw kernel calls — lives in the AI Software layer. This is where commands become workflows, and workflows become usable capabilities.

### 7.1 Multi-agent orchestration

```mermaid
graph TD
    Orchestrator[Orchestration Layer] --> AgentA[Agent: Planner]
    Orchestrator --> AgentB[Agent: Executor]
    Orchestrator --> AgentC[Agent: Verifier]

    AgentA -->|proposes command sequence| Orchestrator
    AgentB -->|dispatches commands| Kernel[qyvaria.py Kernel]
    AgentC -->|validates results| Orchestrator

    Kernel -->|RBAC-checked results| AgentB
    AgentB -->|reports| Orchestrator
    Orchestrator -->|final output| User([User / Qyvaria OS])

    style Kernel fill:#111827,color:#fff
```

Agents in this model do not talk to each other directly — they communicate through the orchestration layer, and any command that needs to actually *do* something is routed down to the kernel, where it is subject to the same RBAC gate described in Section 5.

### 7.2 Workflow execution model

```mermaid
sequenceDiagram
    participant User
    participant Workflow as AI Workflow
    participant Kernel as qyvaria.py
    User->>Workflow: Define task / goal
    Workflow->>Workflow: Decompose into sub-commands
    loop For each sub-command
        Workflow->>Kernel: Dispatch command
        Kernel-->>Workflow: RBAC-checked result
    end
    Workflow->>User: Aggregated output
```

### 7.3 Categories of AI Software modules

| Category | Description | Maturity |
|---|---|---|
| **Command-driven workflows** | Direct, scripted sequences of kernel dispatches for a defined task | Stable |
| **Multi-agent orchestration** | Coordinated agent roles cooperating on a shared, permission-checked command surface | Active development |
| **Local-first tooling** | Utilities designed to run entirely on the user's own machine, with no required hosted backend | Stable |
| **Research modules** | Experimental capabilities, explicitly marked as unstable or exploratory | Experimental |

---

## 8. Qyvaria OS — the AI-Native Browser

**Qyvaria OS** is where the kernel and the AI software layer stop being developer tools and become a product a person can actually open and use.

Most "AI in the browser" experiences today are extensions layered on top of Chrome, Firefox, or Edge — sidebars, popups, and injected scripts running inside a browser that was never designed with AI as a first-class citizen. **Qyvaria OS inverts that relationship.** It is a Chromium-based browser where the AI layer is part of the shell itself, not a guest inside it.

### 8.1 High-level architecture

```mermaid
graph TB
    subgraph Shell["Qyvaria OS Browser Shell (Chromium-based)"]
        UI[Browser UI / Tabs / Omnibox]
        NativePage["chrome://qyvaria-os/ (patched native page)"]
        Launcher[Custom Launcher]
    end

    subgraph Bridge["Local Runtime Bridge"]
        NodeServer[Local Node.js Server]
    end

    subgraph AILayer["Qyvaria AI Software"]
        Orchestrator2[Orchestration Layer]
    end

    subgraph KernelLayer["Kernel"]
        Kernel2[qyvaria.py]
    end

    Launcher --> UI
    Launcher --> NodeServer
    UI --> NativePage
    NativePage <--> NodeServer
    NodeServer <--> Orchestrator2
    Orchestrator2 <--> Kernel2

    style Shell fill:#1e3a8a,color:#fff
    style Bridge fill:#0f766e,color:#fff
    style AILayer fill:#374151,color:#fff
    style KernelLayer fill:#111827,color:#fff
```

### 8.2 The native `chrome://qyvaria-os/` page

Chromium exposes a family of privileged, non-web-reachable internal pages — `chrome://settings`, `chrome://extensions`, `chrome://flags`, and so on. These pages are compiled directly into the browser binary and cannot be reached or spoofed by ordinary web content.

Qyvaria OS extends this same mechanism through source-level patching of the Chromium build, so that `chrome://qyvaria-os/` behaves as a **native, first-class internal page** rather than a bundled extension page or a locally-hosted web app opened in a tab.

```mermaid
flowchart LR
    subgraph Ordinary["Ordinary 'AI Extension' Approach"]
        E1[chrome-extension://id/popup.html] -->|content script injection| E2[Web Page Context]
        E2 -.->|limited, sandboxed access| E3[Browser Internals]
    end

    subgraph QyvariaApproach["Qyvaria OS Approach"]
        Q1["chrome://qyvaria-os/ (compiled-in page)"] -->|native IPC| Q2[Browser Process]
        Q2 <--> Q3[Local Node.js Bridge]
        Q3 <--> Q4[AI Software / Kernel]
    end

    style Ordinary fill:#7f1d1d,color:#fff
    style QyvariaApproach fill:#065f46,color:#fff
```

### 8.3 The local Node.js bridge server

Because a Chromium browser process is sandboxed from the host system by design, Qyvaria OS uses a **local Node.js server**, running alongside the browser, as the bridge between:

- the native `chrome://qyvaria-os/` UI,
- the Qyvaria AI Software orchestration layer, and
- ultimately, the `qyvaria.py` kernel.

```mermaid
sequenceDiagram
    autonumber
    participant Page as chrome://qyvaria-os/
    participant Node as Local Node.js Server
    participant AI as AI Software Layer
    participant K as qyvaria.py Kernel

    Page->>Node: User action (local IPC / HTTP)
    Node->>AI: Forward as structured task
    AI->>K: Dispatch command(s)
    K-->>AI: RBAC-checked result
    AI-->>Node: Aggregated response
    Node-->>Page: Render result in native UI
```

This keeps a clean separation of concerns: the browser shell is responsible for presentation, the Node.js server is responsible for local process bridging, the AI software layer is responsible for orchestration, and the kernel remains the single point of execution and permission enforcement.

### 8.4 Custom launchers

Qyvaria OS ships with **custom launchers** for both supported platforms. A launcher's job is to start the browser shell and the local Node.js bridge server together, as a single coordinated startup sequence, rather than requiring a user to manually start a backend process before opening a browser window.

```mermaid
stateDiagram-v2
    [*] --> LauncherStart
    LauncherStart --> CheckDependencies: Verify Node.js / runtime
    CheckDependencies --> StartNodeServer: Dependencies OK
    CheckDependencies --> Error: Missing dependency
    StartNodeServer --> LaunchBrowserShell
    LaunchBrowserShell --> Ready: chrome://qyvaria-os/ available
    Error --> [*]
    Ready --> [*]
```

### 8.5 Phased development

Qyvaria OS is being developed in explicit phases rather than as a single monolithic release. The current toolkit generation is **Phase 4**.

```mermaid
gantt
    title Qyvaria OS - Toolkit Development Phases
    dateFormat  X
    axisFormat %s

    section Phase 1
    Core browser shell exploration     :done, p1, 0, 1
    section Phase 2
    Local server bridge prototype      :done, p2, 1, 2
    section Phase 3
    Launcher system Win/Linux          :done, p3, 2, 3
    section Phase 4
    Native URL patching groundwork     :active, p4, 3, 5
    section Phase 5
    Full native build pipeline         :p5, 5, 7
```

> **Note on running native builds:** Full native Qyvaria OS builds — particularly the source-patched Chromium variant that enables `chrome://qyvaria-os/` — require a genuine **Linux desktop environment** with substantial build resources (disk space, memory, and CPU time comparable to building Chromium itself). This is expected: Qyvaria OS is not a thin wrapper, it is a real browser build with a custom layer patched into the source tree.

---

## 9. Full-Stack Architecture

Bringing every layer together, the complete Qyvaria stack looks like this end-to-end:

```mermaid
graph TB
    User([User]) --> Shell

    subgraph Shell["Qyvaria OS"]
        direction TB
        UI2[Browser UI]
        Native2["chrome://qyvaria-os/"]
        Launcher2[Custom Launcher]
    end

    Shell --> Node2[Local Node.js Bridge Server]

    subgraph Software["Qyvaria AI Software"]
        direction TB
        Orch[Orchestration Layer]
        Agents[Agent Roles]
        Workflows[Command Workflows]
    end

    Node2 --> Software
    Orch --> Agents
    Orch --> Workflows

    subgraph Kernel3["qyvaria.py Kernel"]
        direction TB
        Parser[CommandParser]
        Router[DispatchRouter]
        RBAC[RBACGate]
        Exec[DeterministicExecutor]
    end

    Software --> Parser
    Parser --> Router --> RBAC --> Exec
    Exec --> Result([Deterministic, Permission-Checked Result])
    Result --> Software
    Software --> Node2
    Node2 --> Shell
    Shell --> User

    style Shell fill:#1e3a8a,color:#fff
    style Software fill:#374151,color:#fff
    style Kernel3 fill:#111827,color:#fff
```

The important invariant, visible in every diagram in this document: **there is exactly one path to execution, and it always passes through the RBAC gate inside the kernel.** Whether the entry point is a terminal command, a scripted AI workflow, or a click inside the Qyvaria OS browser shell, the same guarantees apply every time.

---

## 10. Installation & Usage

### 10.1 Requirements

| Component | Requirement |
|---|---|
| Kernel (`qyvaria.py`) | Python 3.x |
| Qyvaria AI Software | Python 3.x, kernel dependencies from `requirements.txt` |
| Qyvaria OS (packaged) | Node.js 20+ (Windows especially) |
| Qyvaria OS (native/patched build) | Linux desktop environment, Chromium build toolchain, substantial disk/RAM/CPU |

### 10.2 Running the kernel directly

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
pip install -r requirements.txt
python qyvaria.py --subject "your task" --engine generic -n 4
```

For fully reproducible output:

```bash
python qyvaria.py --subject "your task" --engine generic -n 4 --seed 42
```

### 10.3 Launching Qyvaria OS (packaged builds)

Packaged builds are distributed via [GitHub Releases](https://github.com/Havlasek1John/Qyvaria/releases) rather than committed directly to the repository, to keep the source tree lightweight.

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

### 10.4 Verifying a release

Release archives are published alongside checksums. Verify integrity before running any setup script:

```bash
sha256sum -c CHECKSUMS.sha256
```

---

## 11. Repository Layout

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
├─ qyvaria.py                     # The kernel — single-file core
└─ apps/
   └─ qyvaria-os/                 # Qyvaria OS toolkit
      ├─ launchers/                # Platform-specific custom launchers
      ├─ bridge-server/            # Local Node.js bridge server
      └─ patches/                  # Chromium source patches for native chrome://qyvaria-os/
```

Large binaries (Qyvaria OS platform packages, build archives) are intentionally kept out of the committed source tree and published as versioned Release assets.

---

## 12. Project Status

Qyvaria is developed and maintained by a single engineer, in public, on an ongoing basis. Nothing in this repository should be read as a "finished, frozen" product — it is a living system.

| Component | Status | Notes |
|---|---|---|
| Kernel (`qyvaria.py`) | Stable, actively maintained | Currently on the **Varia** generation |
| RBAC dispatch pipeline | Stable | Core security invariant of the whole system |
| Qyvaria AI Software — workflows | Stable | Command-driven workflows in daily use |
| Qyvaria AI Software — multi-agent orchestration | Active development | API surface may change between releases |
| Qyvaria AI Software — research modules | Experimental | Explicitly unstable, subject to removal |
| Qyvaria OS — launchers | Stable | Windows and Linux launchers available |
| Qyvaria OS — local Node.js bridge | Stable | Core bridging mechanism |
| Qyvaria OS — native `chrome://qyvaria-os/` patching | Phase 4, active development | Requires Linux desktop + Chromium build environment |

---

## 13. Comparison: Qyvaria OS vs. Conventional AI-in-Browser Products

```mermaid
graph LR
    subgraph Conventional["Conventional AI Browser Extension"]
        C1[Chrome / Edge / Firefox] --> C2[Extension Sandbox]
        C2 --> C3[Injected Content Script]
        C3 -.->|network call| C4[Remote AI API]
    end

    subgraph QyvariaModel["Qyvaria OS"]
        D1[Chromium-based Shell] --> D2["chrome://qyvaria-os/"]
        D2 --> D3[Local Node.js Bridge]
        D3 --> D4[Local AI Software + Kernel]
    end

    style Conventional fill:#7f1d1d,color:#fff
    style QyvariaModel fill:#065f46,color:#fff
```

| Dimension | Conventional AI Extension | Qyvaria OS |
|---|---|---|
| **Integration depth** | Injected into an existing browser via extension APIs | Compiled into the browser shell via source patching |
| **AI execution location** | Typically remote, via hosted API | Local-first, via kernel + AI software running alongside the browser |
| **Permission model** | Browser extension permission scopes | Kernel-level RBAC, independent of browser extension permissions |
| **Command auditability** | Often opaque, vendor-controlled | Every command traceable through a single, deterministic kernel |
| **Native UI surface** | Popup / sidebar / injected DOM elements | First-class internal page (`chrome://qyvaria-os/`) |
| **Startup model** | Browser starts normally; extension activates separately | Custom launcher starts browser shell and bridge server together |

---

## 14. Roadmap

```mermaid
timeline
    title Qyvaria - Forward Roadmap
    Now       : Phase 4 native patching groundwork
              : RBAC policy auditing tools
    Near-term : Expanded Qyvaria OS launcher and packaging system
              : Stronger multi-agent orchestration APIs
    Mid-term  : Additional kernel generation beyond Varia
              : Full native Chromium build pipeline for Qyvaria OS
    Long-term : Clearer stable and experimental module separation
              : Expanded public documentation and audit tooling
```

- Deeper native Chromium integration for `chrome://qyvaria-os/`
- A more complete Qyvaria OS launcher and packaging system across platforms
- A kernel generation beyond **Varia**, focused on RBAC policy auditing and reporting
- Expanded, versioned documentation for every layer of the stack
- Clearer public labeling of which AI Software modules are stable vs. experimental

---

## 15. Frequently Asked Questions

**Is Qyvaria a company?**
No. Qyvaria is a solo, donation-supported AI engineering project maintained by one person, developed and released publicly.

**Do I need Qyvaria OS to use the kernel?**
No. `qyvaria.py` runs standalone from the command line. Qyvaria OS is a native runtime environment for the AI software, not a requirement for using the kernel itself.

**Can I run Qyvaria OS on Windows without a full Chromium source build?**
Yes — packaged Windows and Linux builds are available via GitHub Releases. Only the fully native, source-patched `chrome://qyvaria-os/` variant requires a Linux build environment.

**Why RBAC instead of a simpler permission model?**
Because Qyvaria is designed to support multiple callers with different trust levels — a human operator, an AI agent, and a read-only browser context — a role-based model scales cleanly, and keeps the enforcement logic inside the kernel rather than scattered across each caller.

**Is the project open source?**
Yes, under the Apache License 2.0. See [Section 18](#18-license).

---

## 16. Credits

**Creator and maintainer**
Jan Havlasek — designer and engineer of the `qyvaria.py` kernel, Qyvaria AI Software, and Qyvaria OS.

**Special thanks**
Jiri Burda, for testing, feedback, and support throughout development.

**Open source foundations**
Qyvaria depends on, and is grateful to, the broader open-source ecosystem — including Python, Node.js, and Chromium — along with the communities that maintain them. Full attribution is in [`THIRD_PARTY_NOTICES.md`](./THIRD_PARTY_NOTICES.md).

---

## 17. Contributing & Support

Contributions, issue reports, and technical feedback are welcome, provided they respect the project's Apache-2.0 licensing, attribution requirements, and a strict no-secrets policy (no API keys, tokens, or private data in issues or pull requests).

- Community discussion: [Qyvaria Forums](https://qyvaria.boards.net/)
- Public project index: [Qyvaria Software Index](https://qyvaria-ai-studio-index.vercel.app/)
- Bug reports and technical issues: [GitHub Issues](https://github.com/Havlasek1John/Qyvaria/issues)

Before opening a pull request, please read [`CONTRIBUTING.md`](./CONTRIBUTING.md), [`SECURITY.md`](./SECURITY.md), and [`CODE_OF_CONDUCT.md`](./CODE_OF_CONDUCT.md).

---

## 18. License

Qyvaria — the kernel, the AI software, and Qyvaria OS — is released under the **Apache License 2.0**.

```
Copyright Jan Havlasek — Qyvaria
Licensed under the Apache License, Version 2.0
https://github.com/Havlasek1John/Qyvaria
```

See [`LICENSE`](./LICENSE) for the full text.

---

<div align="center">

**Qyvaria: one kernel, one dispatch path, one place to look when you need to know why something ran.**

</div>
