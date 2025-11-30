---
title: Mountain Hall 3 Biome
category: biome
---

# Mountain Hall 3 Biome

This document describes the configuration for the "Mountain Hall 3" biome in Noita, focusing on its generation parameters and material composition.

## Topology

The `Topology` element defines the fundamental generation properties of the biome.

### Key Attributes

| Attribute             | Value                                   | Description                                                                 |
| :-------------------- | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `name`                | `_EMPTY_`                               | Internal identifier for this biome configuration.                           |
| `type`                | `BIOME_WANG_TILE`                       | Indicates this biome uses Wang tiles for generation.                        |
| `background_image`    | `data/weather_gfx/background_cave_02.png` | The background image used for this biome.                                   |
| `background_use_neighbor` | `0`                                     | Whether to use neighbor information for background blending.                |
| `lua_script`          | `data/scripts/biomes/mountain/mountain_hall_3.lua` | The Lua script that controls biome-specific logic and events.               |
| `wang_map_width`      | `256`                                   | The width of the Wang tile map used for generation.                         |
| `wang_map_height`     | `256`                                   | The height of the Wang tile map used for generation.                        |
| `coarse_map_force_terrain` | `1`                                     | Forces terrain generation on the coarse map.                                |
| `audio_ambience`      | `cave`                                  | The ambient soundscape associated with this biome.                          |
| `skip_edge_textures`  | `1`                                     | Whether to skip rendering textures on the edges of the biome.               |

## Materials

The `Materials` element defines the various materials and vegetation present within the biome and their distribution.

### Material Components

This section details the different materials that can spawn within the biome, their properties, and spawn conditions.

| Material Name   | `is_rare` | `limit_min_y` | `limit_max_y` | `material_min` | `material_max` | `rare_use_polka` | `rare_use_perlin` |
| :-------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :--------------- | :---------------- |
| `coal`          | `1`       | `100`         | `2048`        | `0.51`         | `0.55`         | `1`              | `0`               |
| `soil`          | `0`       | `-1024`       | `424.229`     | `0.45`         | `0.53`         | `1`              | `0`               |
| `rock_hard`     | `0`       | `100`         | `2048`        | `0.53`         | `0.95`         | `1`              | `0`               |
| `coal` (rare)   | `1`       | `100`         | `2048`        | `1.1`          | `1.2`          | `1`              | `1`               |
| `copper`        | `1`       | `750`         | `2048`        | `1.05`         | `1.25`         | `1`              | `1`               |
| `gold`          | `1`       | `750`         | `2048`        | `1.05`         | `1.2`          | `1`              | `1`               |
| `rock_static`   | `0`       | `100`         | `2048`        | `0.9`          | `3.5`          | `1`              | `0`               |

**Summary of Material Components:**
The biome primarily consists of `soil`, `rock_hard`, and `rock_static`. Rarer materials like `coal`, `copper`, and `gold` are also present, with `copper` and `gold` appearing at higher elevations (`limit_min_y="750"`). Some `coal` spawns with different parameters, suggesting variations in its distribution or properties. The `rare_use_polka` and `rare_use_perlin` attributes indicate the generation methods for these rarer materials.

### Vegetation Components

These components define the visual elements and flora within the biome.

| Component Type      | `is_visual` | `is_grass` | `is_ceiling_plant` | `tree_material`        | `tree_probability` | `material_on_top_of` | `tree_image_file`                               |
| :------------------ | :---------- | :--------- | :----------------- | :--------------------- | :----------------- | :------------------- | :---------------------------------------------- |
| Grass               | `1`         | `1`        | `0`                | `grass`                | `0.828571`         | `soil`               | (empty)                                         |
| Grass               | `1`         | `1`        | `0`                | `moss`                 | `0.828571`         | `sand_static`        | (empty)                                         |
| Ceiling Plant       | `1`         | `0`        | `1`                | `ceiling_plant_material` | `0.24571`          | N/A                  | `data/vegetation/vine_growth_1.xml`             |
| Ceiling Plant       | `1`         | `0`        | `1`                | `ceiling_plant_material` | `0.54571`          | N/A                  | `data/vegetation/ceiling_vegetation_00$[2-8].png` |
| Vegetation (Mushroom) | `1`         | `0`        | `0`                | `plant_material`       | `0.828571`         | N/A                  | `data/vegetation/mushroom_growth_2.xml`         |

**Summary of Vegetation Components:**
The biome features two types of ground-level grass, one requiring `soil` and the other `sand_static`. It also includes ceiling-mounted vegetation, such as vines and other decorative plants, with varying probabilities and image files. A mushroom-like vegetation component is also present. The `visual_color` attribute in these components defines their color tint.