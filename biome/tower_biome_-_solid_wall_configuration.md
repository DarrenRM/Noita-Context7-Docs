---
title: Tower Biome - Solid Wall Configuration
category: biome
---

# Tower Biome - Solid Wall Configuration

This document details the configuration for a specific biome within Noita, focusing on the "Tower" environment and its solid wall generation.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `$biome_tower` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for procedural generation.
*   **`background_image`**: `data/weather_gfx/background_snowcastle.png` - The main background image for the biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: `104` - Controls the layering and rendering order of background elements.
*   **`wang_template_file`**: `data/wang_tiles/snowcastle.png` - The image file containing the Wang Tile patterns used for generating the biome's structure.
*   **`lua_script`**: `data/scripts/biomes/tower.lua` - The script that governs the biome's behavior and generation logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - Dimensions of the generated biome map.
*   **`audio_music_2`**: `tower` - The music track associated with this biome.
*   **`audio_ambience`**: `snowcastle` - The ambient soundscape for the biome.

## Materials

The `<Materials>` element defines the different material components that make up the biome's terrain and their generation properties.

### Key Material Components:

The following table summarizes the primary material components and their key generation parameters.

| Material Name    | Material Index | Min Density | Max Density | Min Y Limit | Max Y Limit | Rare Use Polka | Polka Probability | Polka Radius Low | Polka Radius High |
| :--------------- | :------------- | :---------- | :---------- | :---------- | :---------- | :------------- | :---------------- | :--------------- | :---------------- |
| `snowrock_static`| 9              | 0.9         | 3.6         | 100         | 2048        | 1              | 0.2               | 0.2              | 0.65              |
| `snow_static`    | 10             | 0.53        | 1.05        | 100         | 2048        | 1              | 0.2               | 0.2              | 0.65              |
| `snow_sticky`    | 9              | 0.1         | 0.9         | 50          | 2248        | 0              | N/A               | N/A              | N/A               |
| `ice_static`     | 5              | 0.9         | 3.5         | 100         | 2048        | 1              | 0.1               | 0.8              | 1.8               |

**Summary of Material Generation:**

*   **`snowrock_static`** and **`snow_static`** are common materials (`is_rare="0"`) used throughout the mid-to-upper levels of the biome. They utilize a "polka" distribution pattern for variation.
*   **`snow_sticky`** is a less dense material found at lower Y-coordinates, potentially creating slippery or unique traversal challenges.
*   **`ice_static`** is a rarer material (`is_rare="1"`) that also uses a polka distribution, suggesting it appears in specific, less frequent formations within the biome.
*   **`limit_min_y`** and **`limit_max_y`** define the vertical range within the biome where each material can appear.
*   **`material_min`** and **`material_max`** control the density or thickness of the material.
*   **`rare_use_polka`**, **`rare_polka_probability`**, **`rare_polka_radius_low`**, and **`rare_polka_radius_high`** are parameters that govern the clustered or "polka-dot" distribution of rarer material variants.