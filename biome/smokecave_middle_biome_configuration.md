---
title: Smokecave Middle Biome Configuration
category: biome
---

# Smokecave Middle Biome Configuration

This document details the configuration for the "Smokecave Middle" biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental generation properties of the biome.

### Key Attributes

| Attribute             | Value                                  | Description                                                                 |
| :-------------------- | :------------------------------------- | :-------------------------------------------------------------------------- |
| `name`                | `_EMPTY_`                              | Internal identifier for this topology configuration.                        |
| `type`                | `BIOME_WANG_TILE`                      | Specifies the biome generation method (Wang tiles).                         |
| `background_image`    | `data/weather_gfx/background_cave_02.png` | Path to the background image used for this biome.                           |
| `background_use_neighbor` | `0`                                    | Indicates if the background should blend with neighboring biomes (0 = no). |
| `wang_template_file`  | `""`                                   | Path to the Wang tile template file (empty here, likely handled by script). |
| `lua_script`          | `data/scripts/biomes/smokecave_middle.lua` | The Lua script that governs the biome's dynamic behavior and generation.    |
| `wang_map_width`      | `256`                                  | The width of the generated Wang tile map for this biome.                    |
| `wang_map_height`     | `256`                                  | The height of the generated Wang tile map for this biome.                   |
| `coarse_map_force_terrain` | `1`                                    | Forces terrain generation on the coarse map.                                |

## Materials

The `Materials` element defines the types and distribution of materials within the biome. Each `MaterialComponent` specifies how a particular material is placed and its properties.

### Key Material Components

| Material Name     | Enabled | Rarity | Min Y | Max Y | Material Max | Material Min | Polka Probability | Scale X | Scale Y | Use Perlin | Use Polka |
| :---------------- | :------ | :----- | :---- | :---- | :----------- | :----------- | :---------------- | :------ | :------ | :--------- | :-------- |
| `coal`            | 1       | 1      | 100   | 2048  | 0.55         | 0.51         | 0.160871          | 0.0100004 | 0.00357165 | 0          | 1         |
| `rock_hard`       | 1       | 0      | 100   | 2048  | 0.95         | -100.0       | 0.2               | 0.05    | 0.05    | 0          | 1         |
| `coal` (rare)     | 1       | 1      | 100   | 2048  | 1.2          | 1.1          | 0.157143          | 0.0214286 | 0.0214286 | 1          | 1         |
| `copper`          | 1       | 1      | 750   | 2048  | 1.25         | 1.05         | 0.357143          | 0.007514286 | 0.007514286 | 1          | 1         |
| `rock_hard_border`| 1       | 0      | 100   | 2048  | 3.5          | -0.25        | 0.2               | 0.05    | 0.05    | 0          | 1         |

#### Material Component Attributes Explained

*   `_enabled`: Whether this material component is active (1) or not (0).
*   `is_rare`: Indicates if the material is considered rare (1) or common (0).
*   `limit_min_y`, `limit_max_y`: Vertical bounds within which this material can appear.
*   `material_max`, `material_min`: The range of values used to determine the density or presence of the material.
*   `material_name`: The name of the material being configured (e.g., `coal`, `rock_hard`).
*   `rare_polka_probability`: The probability of the "polka" pattern appearing for rare materials.
*   `rare_polka_radius_high`, `rare_polka_radius_low`: Defines the radius range for the polka pattern.
*   `rare_scale_x`, `rare_scale_y`: Scaling factors for the material's distribution pattern.
*   `rare_use_perlin`: Whether Perlin noise is used to influence the material's distribution (1) or not (0).
*   `rare_use_polka`: Whether a polka pattern is used for distribution (1) or not (0).

---