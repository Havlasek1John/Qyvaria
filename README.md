# Qyvaria

<p align="center">
  <img src="https://img.shields.io/badge/Qyvaria-Prompt%20Kernel-8A2BE2?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Type-Single%20File%20AI%20Runtime-black?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/Focus-Prompt%20Engineering-00BFFF?style=for-the-badge"/>
  <img src="https://img.shields.io/badge/License-Apache%202.0-blue.svg?style=for-the-badge"/>
</p>

---

## Overview

**Qyvaria** is a single-file AI prompt generation kernel designed to transform structured intent into high-quality, engine-ready prompts for generative AI systems.

It acts as a **prompt synthesis runtime**, bridging human ideas and image-generation engines like:

- SDXL pipelines
- MidJourney-style systems
- Flux workflows
- Generic text-to-image models

---

## Core Concept

Qyvaria is built around a **Prompt Kernel Architecture**:

> Input → Structured Prompt Spec → Style Engine → Camera/Lighting System → Engine Wrapper → Final Prompt Output

This allows:
- Reproducible prompts
- Cross-model compatibility
- Deterministic or randomized generation
- Scalable prompt engineering workflows

---

## Features

### 🎨 Style System
Built-in creative and technical styles:
- Cinematic
- Photorealistic
- Product photography
- Interior / architecture
- Anime
- Macro
- Blueprint / diagram
- Vector / UI mock
- Watercolor

Each style influences:
- Lighting setup
- Camera configuration
- Composition rules
- Negative prompt generation

---

### ⚙️ Multi-Engine Support

- **SDXL** → structured prompt + negative prompt + parameters  
- **MidJourney** → compact stylized CLI format  
- **Flux** → JSON-style guided generation  
- **Generic** → clean universal prompt output  

---

### 🎲 Reproducibility System
- Seed-based deterministic output
- Controlled randomness
- Batch generation support (`-n` runs)

---

### 🚫 Intelligent Negative Prompting
Automatically generated based on:
- Style type
- Engine constraints
- Quality filters (blur, artifacts, distortion, etc.)

---

## Installation

```bash
git clone https://github.com/Havlasek1John/Qyvaria.git
cd Qyvaria
python qyvaria.py --help
