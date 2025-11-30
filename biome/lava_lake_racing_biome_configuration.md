---
title: Lava Lake Racing Biome Configuration
category: biome
---

# Lava Lake Racing Biome Configuration

This document details the configuration for the "Lava Lake Racing" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies that this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_cave_04_alt.png` - The primary background texture for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: These define the specific edge textures used to seamlessly connect background elements.
*   **`background_edge_priority`**: `10` - Controls the layering of background edges.
*   **`lua_script`**: `data/scripts/biomes/lavalake_racing.lua` - The associated Lua script that governs biome behavior and generation logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - The dimensions of the Wang map used for biome generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`audio_ambience`**: `cave` - Sets the ambient soundscape for this biome.

## Materials

The `Materials` element defines the different material components that can appear within this biome and their generation parameters.

### Key Material Components:

The following table summarizes the key `MaterialComponent` elements and their significant attributes.

| Material Name      | `is_rare` | `limit_min_y` | `limit_max_y` | `material_min` | `material_max` | `rare_use_polka` | `rare_use_perlin` |
| :----------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :--------------- | :---------------- |
| `coal`             | `1`       | `100`         | `2048`        | `0.51`         | `0.55`         | `1`              | `0`               |
| `rock_hard`        | `0`       | `100`         | `2048`        | `0.53`         | `0.95`         | `1`              | `0`               |
| `rock_hard_border` | `0`       | `100`         | `2048`        | `0.9`          | `3.5`          | `1`              | `0`               |
| `coal`             | `1`       | `100`         | `2048`        | `1.1`          | `1.2`          | `1`              | `1`               |
| `copper`           | `1`       | `750`         | `2048`        | `1.05`         | `1.25`         | `1`              | `1`               |

### Material Component Attributes Explained:

*   **`material_name`**: The name of the material to be generated (e.g., `coal`, `rock_hard`, `copper`).
*   **`is_rare`**: `1` if the material is considered rare, `0` otherwise.
*   **`limit_min_y`, `limit_max_y`**: Vertical bounds within which this material can spawn.
*   **`material_min`, `material_max`**: The minimum and maximum density or probability of the material appearing.
*   **`rare_use_polka`**: `1` if polka noise is used for distribution of rare materials, `0` otherwise.
*   **`rare_use_perlin`**: `1` if Perlin noise is used for distribution of rare materials, `0` otherwise.
*   **`rare_polka_probability`**: The probability of the material appearing when using polka noise.
*   **`rare_polka_radius_low`, `rare_polka_radius_high`**: Controls the clustering of rare materials when using polka noise.
*   **`rare_scale_x`, `rare_scale_y`**: Scaling factors for the noise patterns used in material distribution.

This configuration suggests a biome with a base of hard rock and coal, with rarer occurrences of coal and copper at higher elevations, utilizing noise patterns for distribution.