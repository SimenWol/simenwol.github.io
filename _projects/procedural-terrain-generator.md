---
layout: project
title: "Custom Procedural Terrain Generator"
date: 2025-01-24
categories: [projects]
image: /assets/images/Y2B/main.png
description: "Custom Procedural Terrain Generator was a solo research project, implemented in a custom ECS-based C++ game engine."
contributions: "Height-Based Terrain Generation using Perlin Noise | Texture Support | Terrain-specific Renderpass | Biomes & Biome Blending | Chunking | LOD through Tesselation Shaders | Blogpost"
tools: "FastNoiseLite | GLM | OpenGL | GLSL (Vertex, Fragment & Tesselation Shaders) | ImGui | EnTT"
tags:
  - "C++"
  - "CUSTOM ENGINE"
  - "SOLO PROJECT"
team_size: "Solo"
platforms:
  - "Windows"
duration: "8 weeks (Nov 2024 - Jan 2025)"
---
## 🌍 Custom Procedural Terrain Generator - Runtime Infinite Terrain in a Custom C++ ECS Engine

*Custom Procedural Terrain Generator* was a solo technical research project exploring scalable terrain generation inside a custom ECS-based C++ game engine. The goal was to design a flexible system capable of generating large continuous worlds while maintaining performance and visual clarity.

Custom Procedural Terrain Generator was a solo technical research project focused on building a scalable, extensible runtime terrain generation pipeline inside a custom ECS-based C++ engine.

The project explores procedural heightmap generation, chunk streaming, GPU-driven terrain rendering, biome systems, tessellation-based LOD, and architecture design for reusable engine systems. The system is designed to be modular, easy to embed into new projects, and highly configurable through runtime tooling.ws.

A technical blogpost documenting some research decisions, implementation challenges, and lessons learned can be found here:
<a href="https://medium.com/@simenwolters/creating-endless-worlds-with-procedural-terrain-generation-bc8568078266" target="_blank">Read the development blogpost.</a>

---

<!-- ## My Contributions -->

<!-- ---

## Core Terrain Generation
The generator produces a heightmap using layered noise functions. Terrain data is generated deterministically using seeded noise and converted into runtime meshes with correct normal calculation sampled directly from the noise gradient.

### Mesh Generation & Normals
Meshes are generated directly from heightmap samples, with normals computed from offset noise sampling rather than post-process recalculation. This produces consistent lighting while avoiding expensive recalculation passes.

**Key Decisions:**
- Sample normals directly from noise gradient.
- Avoid recomputing normals after mesh generation.
- Keep generation deterministic per chunk.

**Challenges:**
- Ensuring stable gradients across chunk borders.
- Maintaining consistent shading across chunks & LOD changes.

---

## Terrain Texturing & Colouring
The system supports both texture-based and colour-only rendering, including texture blending. Textures are applied based on height ranges & biomes.

**Features:**
- Height-based texture assignment.
- Adjustable tiling scale.
- Runtime toggle between textures and colour mode.
- Support for temperature/biome driven layers.

---

## Chunk Streaming & Infinite Terrain
Terrain meshes are generated in chunks which can be tiled infinitely. Chunk generation is driven by the camera position and configurable render distance.

**System Behaviour:**
- Generate only chunks near the camera
- Destroy chunks outside render distance
- Regenerate chunks deterministically when revisiting areas

**Future Direction:**
- Persistent world saving
- Mesh reconstruction without regeneration

---

## Biome System
Biomes are defined using height and temperature ranges. The system supports an arbitrary number of biomes without requiring structural changes.

**Features:**
- Flexible biome definitions
- Automatic biome assignment
- Height + temperature driven placement
- Runtime biome tinting and blending (GPU stage)

---

## Terrain Shaping & Customisation Features
**Terraces / Plateaus:**
Noise layers can be individually terraced to produce stylized terrain formations such as plateaus and stepped cliffs.

**Design Tradeoffs:**
- Increased architectural complexity
- Greater flexibility for per-layer control
- Easier expansion for future generation features

**Additional Terrain Controls:**
- Exponent shaping for valleys/peaks
- Height inversion and absolute modifiers
- Vertical scaling & translation
- Layer-based procedural adjustments
- These controls allow highly varied terrain generation from a single core system.

---
---
---
--- -->

<!-- ## My Contributions

- Designed and implemented full procedural terrain generation pipeline
- Perlin-noise based heightmap generation using FastNoiseLite
- Biome system with blended transitions
- Chunk-based terrain streaming
- Level-of-detail system using GPU tessellation shaders
- Terrain-specific rendering pipeline & shader setup
- Texture integration & material blending
- Research documentation and technical blog writing

---

### Terrain Generation System
**Purpose:**  
Generate scalable terrain data capable of supporting large continuous environments with adjustable parameters for experimentation and research.

**Key Features:**
- Height-based generation using layered noise
- Adjustable generation parameters through ImGui tooling
- Deterministic terrain generation
- Real-time regeneration for rapid iteration

**Challenges:**
- Preventing visible noise repetition
- Maintaining stable terrain transitions
- Keeping generation fast enough for interactive tweaking

---

### Biomes & Biome Blending
**Purpose:**  
Introduce visual and structural diversity across terrain regions without harsh transitions.

**Key Features:**
- Biome classification driven by noise layers
- Smooth interpolation between biome regions
- Support for biome-based texture variation
- Modular biome definitions for experimentation

**Challenges:**
- Avoiding obvious biome borders
- Balancing biome distribution
- Maintaining coherent terrain shapes across biome blends

---

### Chunking & World Streaming
**Purpose:**  
Allow terrain to scale beyond a single mesh by dynamically loading and unloading terrain sections.

**Key Features:**
- Chunk-based terrain structure
- Camera-driven chunk activation
- Data separation between generation and rendering
- Foundation for endless world streaming

**Challenges:**
- Preventing visible seams between chunks
- Managing memory usage
- Synchronizing generation and render updates

---

### LOD System — Tessellation-Based Detail
**Purpose:**  
Maintain high visual fidelity close to the camera while minimizing GPU cost at distance.

**Key Features:**
- GPU tessellation shaders for adaptive geometry density
- Distance-based tessellation scaling
- Smooth transitions between detail levels
- Integrated terrain render pass support

**Challenges:**
- Avoiding popping during LOD transitions
- Maintaining stable normals across tessellation levels
- Balancing performance vs visual quality

---

### Terrain Rendering Pipeline
**Purpose:**  
Provide a dedicated rendering workflow optimized for terrain materials and large meshes.

**Key Features:**
- Terrain-specific render pass
- Texture blending based on terrain data
- GLSL shader pipeline (vertex, fragment, tessellation)
- Debug visualization tools via ImGui

**Challenges:**
- Managing shader complexity
- Ensuring compatibility with ECS architecture
- Keeping render logic modular within engine structure

---

### Key Concepts
- **Procedural generation pipelines** for scalable world creation
- **GPU-driven level of detail** using tessellation shaders
- **Chunk-based streaming architectures**
- **Biome-based terrain variation**
- **Custom render passes within ECS-driven engines**
- **Tooling-driven iteration using ImGui**

---

### Overall Impact
Working on the *Custom Procedural Terrain Generator* strengthened my understanding of procedural content generation, GPU-based rendering techniques, and large-scale system architecture within a custom engine environment. The project reinforced the importance of balancing flexibility, performance, and visual consistency when designing scalable real-time systems.

-->
## More information soon!