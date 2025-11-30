---
title: Water Cave Biome Configuration
category: biome
---

# Water Cave Biome Configuration

This document details the configuration for the "Water Cave" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies that this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_cave_04_alt.png` - The primary background image for the biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background, allowing for seamless transitions.
*   **`background_edge_priority`**: `11` - Determines the rendering order of background edges. Higher values are drawn on top.
*   **`background_use_neighbor`**: `0` - Disables the use of neighbor tiles to determine background variations.
*   **`lua_script`**: `data/scripts/biomes/watercave.lua` - The associated Lua script that controls dynamic behavior and events within this biome.
*   **`wang_map_width`, `wang_map_height`**: `256` - The dimensions of the internal map used for Wang Tile generation.
*   **`audio_music_2`**: `watercave` - The name of the music track to play in this biome.
*   **`audio_ambience`**: `wandcave` - The name of the ambient soundscape for the biome.
*   **`fog_of_war_type`**: `HEAVY_NO_CLEAR` - Defines the fog of war behavior, indicating a heavy, uncleared fog.

## Materials

The `Materials` element defines the distribution and properties of various materials within the biome.

### Key Material Components:

The following table summarizes the key `MaterialComponent` entries. Each component defines how a specific material is generated and its properties.

| Material Name   | Enabled | Is Rare | Min Y Limit | Max Y Limit | Material Min | Material Max | Polka Probability | Scale X | Scale Y | Use Perlin | Use Polka |
| :-------------- | :------ | :------ | :---------- | :---------- | :----------- | :----------- | :---------------- | :------ | :------ | :--------- | :-------- |
| `coal`          | 1       | 1       | 100         | 2048        | 0.51         | 0.55         | 0.160871          | 0.0100004 | 0.00357165 | 0          | 1         |
| `rock_hard`     | 1       | 0       | 100         | 2048        | -100.0       | 0.95         | 0.2               | 0.05    | 0.05    | 0          | 1         |
| `coal`          | 1       | 1       | 100         | 2048        | 1.1          | 1.2          | 0.157143          | 0.0214286 | 0.0214286 | 1          | 1         |
| `copper`        | 1       | 1       | 750         | 2048        | 1.05         | 1.25         | 0.357143          | 0.007514286 | 0.007514286 | 1          | 1         |
| `rock_static`   | 1       | 0       | 100         | 2048        | -0.25        | 3.5          | 0.2               | 0.05    | 0.05    | 0          | 1         |

**Summary of Other Material Components:**

*   Additional `coal` components exist with varying rarity, distribution limits, and generation parameters.
*   The biome primarily uses `coal`, `rock_hard`, `rock_static`, and `copper`.
*   `rare_polka_probability`, `rare_polka_radius_high`, `rare_polka_radius_low`, `rare_required_min`, `rare_required_max`, `rare_scale_x`, and `rare_scale_y` are parameters that influence the distribution pattern and density of rare materials, often using a polka-dot-like noise.
*   `rare_use_perlin` and `rare_use_polka` control whether Perlin noise or polka noise is used for generating the material's distribution.