---
title: Spliced Tree Biome Generation
category: biome
---

# Spliced Tree Biome Generation

This document outlines the process for generating the "Spliced Tree" biome in Noita, as defined by the `_tree.bat` script. This script utilizes a specific image file to define the biome's structure and then processes it using `wizard_physics.exe`.

## Core Generation Process

The primary function of this script is to take a pixel scene (`tree.png`) and convert it into a biome definition.

### Key Command

```bash
wizard_physics.exe -splice_pixel_scene data/biome_impl/spliced/tree.png -x -2048 -y -1324
```

*   **`wizard_physics.exe`**: The Noita executable used for processing game data, including biome generation.
*   **`-splice_pixel_scene`**: This flag indicates that the following argument is a pixel scene image to be used for biome generation.
*   **`data/biome_impl/spliced/tree.png`**: The input image file that defines the visual and structural elements of the biome. The colors within this image are interpreted by the game to determine material placement, entity spawning, and other biome characteristics.
*   **`-x -2048 -y -1324`**: These parameters likely define the offset or position where this biome is "spliced" or integrated into the game world.

## Input Image Interpretation (`tree.png`)

The `tree.png` image is crucial. Each pixel's color value corresponds to specific game elements. While the exact mapping is extensive and not fully detailed here, key interpretations include:

*   **Material Definitions**: Different colors represent various materials (e.g., dirt, stone, wood, water).
*   **Entity Spawning**: Specific colors can trigger the spawning of predefined entities or enemy types.
*   **Structural Elements**: The arrangement of colors dictates the shape and layout of the biome, including terrain features.

## AI-Assisted Modding Considerations

For AI-assisted modding, understanding the color-to-game-element mapping of `tree.png` is paramount.

### Key Areas for AI Focus

1.  **Color Palette Analysis**: The AI can analyze the `tree.png` to identify the range of colors used and their frequency. This helps in understanding the dominant materials and themes of the biome.
2.  **Pattern Recognition**: Identifying recurring patterns of colors can reveal common structures or entity placement strategies within the biome.
3.  **Material Mapping Assistance**: Given a color from `tree.png`, the AI could potentially suggest or confirm the corresponding Noita material or entity.
4.  **Procedural Generation Integration**: If a mod aims to procedurally generate biomes, the AI can learn from existing `tree.png` files to create new, similar biome structures.
5.  **Modification of Existing Biomes**: AI can assist in modifying `tree.png` by suggesting color changes to alter material types, or by adding new color regions to introduce new elements.

This script represents a fundamental method of biome definition in Noita, relying heavily on visual input for its construction.