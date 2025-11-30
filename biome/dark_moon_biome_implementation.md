---
title: Dark Moon Biome Implementation
category: biome
---

# Dark Moon Biome Implementation

This document details the implementation of the "Dark Moon" biome within Noita, focusing on its visual and environmental characteristics as defined by its pixel scene data.

## Core Visuals

The Dark Moon biome is primarily defined by its visual representation in a pixel scene.

### Pixel Scene Definition

*   **File:** `moon_dark.png`
*   **Location:** `data/biome_impl/spliced/`
*   **Offset:** The biome's visual elements are placed at coordinates `x=0`, `y=37512` within the game's world. This indicates a specific, likely high-altitude or distinct layer, placement for this biome.

## Key Attributes (Inferred from context)

While the provided data is minimal, the name "Dark Moon" and its placement suggest the following key attributes:

*   **Atmosphere:** Likely dark, possibly with low visibility, and potentially featuring unique atmospheric effects.
*   **Terrain:** The visual data in `moon_dark.png` would define the specific shapes, colors, and textures of the terrain in this biome.
*   **Lighting:** Expected to be dim, with potential for unique light sources or shadows.
*   **Enemies/Hazards:** The biome's theme suggests the presence of specific enemies or environmental hazards suited to a dark, lunar setting.
*   **Materials:** Unique materials might be present, contributing to the biome's distinct feel and gameplay mechanics.

## Implementation Details

The `wizard_physics.exe` tool is used to splice the visual data of this biome into the game's engine.

### Splicing Command

```bash
wizard_physics.exe -splice_pixel_scene data/biome_impl/spliced/moon_dark.png -x 0 -y 37512
```

This command instructs the game engine to load and integrate the pixel data from `moon_dark.png` as a component of the game world at the specified coordinates.