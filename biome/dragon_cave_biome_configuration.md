---
title: Dragon Cave Biome Configuration
category: biome
---

# Dragon Cave Biome Configuration

This document details the configuration for the Dragon Cave biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental generation properties of the biome.

### Key Attributes

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `name`                | Internal identifier for the biome (`$biome_dragoncave`).                    |
| `type`                | Biome generation type (`BIOME_WANG_TILE`).                                  |
| `background_image`    | Path to the background image used for this biome.                           |
| `background_use_neighbor` | Controls if the background image should blend with neighboring biomes (0 = no). |
| `lua_script`          | Path to the Lua script that governs biome-specific behaviors.               |
| `wang_map_width`      | Width of the biome's internal map grid.                                     |
| `wang_map_height`     | Height of the biome's internal map grid.                                    |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map (1 = yes).                    |
| `audio_ambience`      | Sound ambience tag for the biome (`cave`).                                  |
| `skip_edge_textures`  | Whether to skip textures on biome edges (1 = yes).                          |

## Materials

The `Materials` element defines how different materials are distributed within the biome. Each `MaterialComponent` specifies parameters for a particular material.

### Key Material Components

| Material Name      | `is_rare` | `limit_min_y` | `limit_max_y` | `material_max` | `material_min` | `rare_polka_probability` | `rare_scale_x` | `rare_scale_y` | `rare_use_polka` | `rare_use_perlin` |
| :----------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :----------------------- | :------------- | :------------- | :--------------- | :---------------- |
| `coal`             | 1         | 100           | 2048          | 0.55           | 0.51           | 0.160871                 | 0.0100004      | 0.00357165     | 1                | 0                 |
| `rock_hard`        | 0         | 100           | 2048          | 0.95           | -100.0         | 0.2                      | 0.05           | 0.05           | 1                | 0                 |
| `coal` (secondary) | 1         | 100           | 2048          | 1.2            | 1.1            | 0.157143                 | 0.0214286      | 0.0214286      | 1                | 1                 |
| `copper`           | 1         | 750           | 2048          | 1.25           | 1.05           | 0.357143                 | 0.007514286    | 0.007514286    | 1                | 1                 |
| `rock_hard_border` | 0         | 100           | 2048          | 3.5            | -0.25          | 0.2                      | 0.05           | 0.05           | 1                | 0                 |

**Summary of Material Distribution:**

*   **Coal:** Appears in two configurations: a primary, less dense distribution (`is_rare=1`) and a secondary, denser distribution (`is_rare=1`) with Perlin noise.
*   **Rock Hard:** Forms the base terrain (`is_rare=0`) and its borders (`is_rare=0`).
*   **Copper:** Is a rarer material (`is_rare=1`) found at higher elevations (`limit_min_y=750`) and uses both polka and Perlin noise for distribution.

**Note:** Many attributes like `rare_polka_radius_high`, `rare_polka_radius_low`, `rare_required_max`, `rare_required_min`, and `limit_y` are present but not exhaustively listed for brevity. These control the fine-grained placement and density of rare materials.