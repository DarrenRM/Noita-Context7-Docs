---
title: Smokecave Right Biome Configuration
category: biome
---

# Smokecave Right Biome Configuration

This document details the configuration for the `smokecave_right.xml` biome file, focusing on its core attributes and material distribution.

## Topology

The `Topology` element defines the fundamental properties of the biome, including its visual and scripting aspects.

### Key Attributes

| Attribute             | Value                                 | Description                                                                 |
| :-------------------- | :------------------------------------ | :-------------------------------------------------------------------------- |
| `name`                | `_EMPTY_`                             | Internal identifier for the topology.                                       |
| `type`                | `BIOME_WANG_TILE`                     | Specifies the biome generation method (Wang tiles).                         |
| `background_image`    | `data/weather_gfx/background_cave_02.png` | Path to the background image used for this biome.                           |
| `background_use_neighbor` | `0`                                   | Determines if the background image should adapt to neighboring biomes.      |
| `lua_script`          | `data/scripts/biomes/smokecave_right.lua` | Path to the Lua script that controls biome-specific behaviors and events. |
| `wang_map_width`      | `256`                                 | Width of the Wang tile map used for generation.                             |
| `wang_map_height`     | `256`                                 | Height of the Wang tile map used for generation.                            |
| `coarse_map_force_terrain` | `1`                                   | Forces terrain generation on the coarse map.                                |

## Materials

The `Materials` element defines the distribution and properties of various materials within the biome.

### Key Material Components

The following table summarizes the key `MaterialComponent` elements, highlighting their primary material and distribution characteristics.

| Material Name     | Enabled | Is Rare | Min Y | Max Y | Material Max | Material Min | Probability (Rare Polka) | Scale X | Scale Y | Use Perlin | Use Polka |
| :---------------- | :------ | :------ | :---- | :---- | :----------- | :----------- | :----------------------- | :------ | :------ | :--------- | :-------- |
| `coal`            | 1       | 1       | 100   | 2048  | 0.55         | 0.51         | 0.160871                 | 0.0100004 | 0.00357165 | 0          | 1         |
| `rock_hard`       | 1       | 0       | 100   | 2048  | 0.95         | -100.0       | 0.2                      | 0.05    | 0.05    | 0          | 1         |
| `coal`            | 1       | 1       | 100   | 2048  | 1.2          | 1.1          | 0.157143                 | 0.0214286 | 0.0214286 | 1          | 1         |
| `copper`          | 1       | 1       | 750   | 2048  | 1.25         | 1.05         | 0.357143                 | 0.007514286 | 0.007514286 | 1          | 1         |
| `rock_hard_border`| 1       | 0       | 100   | 2048  | 3.5          | -0.25        | 0.2                      | 0.05    | 0.05    | 0          | 1         |

**Summary of Other Material Components:**

*   Additional `coal` components exist with varying rarity and distribution parameters.
*   The `rock_hard` material has a component with a wider distribution range.
*   The `copper` material has a component specifically limited to higher Y-coordinates.

### Key Attributes for `MaterialComponent`

*   `_enabled`: Whether the material component is active.
*   `is_rare`: If the material is considered rare.
*   `limit_min_y`, `limit_max_y`: Vertical bounds for material placement.
*   `material_name`: The name of the material (e.g., `coal`, `rock_hard`, `copper`).
*   `material_max`, `material_min`: The maximum and minimum density/influence of the material.
*   `rare_polka_probability`: Probability of the material appearing in a "polka" pattern when rare.
*   `rare_scale_x`, `rare_scale_y`: Scaling factors for the rare material's distribution.
*   `rare_use_perlin`: Whether Perlin noise is used for distribution.
*   `rare_use_polka`: Whether a "polka" distribution pattern is used.