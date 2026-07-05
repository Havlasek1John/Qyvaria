# Qyvaria

<p align="center">
  <img src="https://img.shields.io/badge/Qyvaria-AI%20Kernel-blueviolet?style=for-the-badge" />
  <img src="https://img.shields.io/badge/Type-Single%20File%20Python%20Runtime-green?style=for-the-badge" />
  <img src="https://img.shields.io/badge/License-Apache%202.0-blue?style=for-the-badge" />
</p>

---

## Overview

**Qyvaria** is an open-source AI engineering runtime built around a single-file Python kernel (`qyvaria.py`). It is designed as a modular prompt-generation and orchestration system for image-generation workflows, multi-engine prompt structuring, and AI experimentation.

Rather than being a traditional application, Qyvaria acts as a **lightweight AI kernel layer** that transforms structured input (subjects, styles, environments, and parameters) into deterministic or semi-randomized prompt systems for downstream generative engines such as SDXL, MidJourney-style pipelines, Flux, or generic text-to-image systems.

---

## Core Concept

Qyvaria is built on the idea of a **Prompt Kernel Architecture**:

- A structured input (`PromptSpec`)
- A style system (cinematic, photoreal, anime, diagram, etc.)
- Engine abstraction layer (SDXL / MidJourney / Flux / Generic)
- Deterministic randomness via seed control
- Negative prompt synthesis system
- Output serialization (CLI / JSON / TXT)

This enables reproducible prompt generation across different AI image systems.

---

## Key Features

### 🎨 Prompt Generation Engine
Automatically constructs high-quality prompts from structured inputs:
- Subject-driven prompt synthesis
- Style packs (cinematic, photoreal, anime, vector, diagram, etc.)
- Lighting, composition, and camera system presets
- Material and environment augmentation

### ⚙️ Multi-Engine Support
Qyvaria supports multiple generation backends:
- **SDXL-style pipelines**
- **MidJourney-style formatting**
- **Flux-compatible structure**
- **Generic prompt output mode**

### 🎲 Deterministic Randomization
- Seed-based reproducibility
- Controlled variation across outputs
- Multi-prompt batch generation (`-n` parameter)

### 🧠 Style Intelligence System
Predefined style packs include:
- Cinematic
- Photoreal
- Product photography
- Interior design
- Architecture
- Macro
- Watercolor
- Pixel / vector / blueprint / UI mock

### 📦 CLI-First Design
Qyvaria is fully controllable via command-line interface:
- JSON or text output modes
- Batch generation support
- Engine selection flags
- Fully scriptable workflow integration

---

## Installation

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
python qyvaria.py --help
