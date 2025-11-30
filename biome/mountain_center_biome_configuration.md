---
title: Mountain Center Biome Configuration
category: biome
---

# Mountain Center Biome Configuration

This document details the configuration for the "Mountain Center" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies that this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - The background image used for this biome.
*   **`wang_template_file`**: `data/wang_tiles/coalmine.png` - The Wang Tile image defining the biome's structure.
*   **`lua_script`**: `data/scripts/biomes/mountain/mountain_center.lua` - The associated Lua script for biome-specific logic.
*   **`wang_map_width` / `wang_map_height`**: `256` - Dimensions of the Wang Tile map.
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.
*   **`skip_edge_textures`**: `1` - Prevents textures from appearing on the biome's edges.

## Materials

The `Materials` element defines the various materials and vegetation present within the biome.

### Key Material Components:

This section lists the primary materials and their distribution within the biome.

| Material Name   | `is_rare` | `material_min` | `material_max` | `limit_min_y` | `limit_max_y` | `add_perlin` | `add_perlin_scale_y` | `add_perlin_scale_x` |
| :-------------- | :-------- | :------------- | :------------- | :------------ | :------------ | :----------- | :------------------- | :------------------- |
| `coal`          | `1`       | `0.51`         | `0.55`         | `100`         | `2048`        | `0`          | `0`                  | `0`                  |
| `soil`          | `0`       | `0.45`         | `0.53`         | `-1024`       | `424.229`     | `0`          | `0`                  | `0`                  |
| `sand_static`   | `0`       | `0.53`         | `1.55`         | `100`         | `2048`        | `0`          | `0`                  | `0`                  |
| `coal` (rare)   | `1`       | `1.1`          | `1.2`          | `100`         | `2048`        | `0`          | `0`                  | `0`                  |
| `copper`        | `1`       | `1.05`         | `1.25`         | `750`         | `2048`        | `0`          | `0`                  | `0`                  |
| `gold`          | `1`       | `1.05`         | `1.2`          | `750`         | `2048`        | `0`          | `0`                  | `0`                  |
| `rock_static`   | `0`       | `0.9`          | `3.5`          | `100`         | `2048`        | `1`          | `0.02`               | `0.01`               |

**Note:** Rare materials often have additional parameters like `rare_polka_probability`, `rare_polka_radius_high`, `rare_polka_radius_low`, `rare_scale_x`, `rare_scale_y`, `rare_use_perlin`, and `rare_use_polka` which control their distribution and visual patterns.

### Vegetation Components:

These components define the flora found within the biome.

*   **Grass (Type 1)**:
    *   `is_visual`: `1`
    *   `tree_material`: `grass`
    *   `tree_probability`: `0.828571`
    *   `material_on_top_of`: `soil`
*   **Grass (Type 2)**:
    *   `is_visual`: `1`
    *   `tree_material`: `moss`
    *   `tree_probability`: `0.828571`
    *   `grass_requires_neighbors`: `1`
    *   `material_on_top_of`: `sand_static`
*   **Ceiling Plant (Type 1)**:
    *   `is_visual`: `1`
    *   `tree_image_file`: `data/vegetation/vine_growth_1.xml`
    *   `tree_material`: `ceiling_plant_material`
    *   `tree_probability`: `0.24571`
    *   `is_ceiling_plant`: `1`
*   **Ceiling Plant (Type 2)**:
    *   `is_visual`: `1`
    *   `tree_image_file`: `data/vegetation/ceiling_vegetation_00$[2-8].png`
    *   `tree_material`: `ceiling_plant_material`
    *   `tree_probability`: `0.54571`
    *   `is_ceiling_plant`: `1`
*   **Mushroom Growth**:
    *   `is_visual`: `1`
    *   `tree_image_file`: `data/vegetation/mushroom_growth_2.xml`
    *   `tree_material`: `plant_material`
    *   `tree_probability`: `0.828571`

**Note:** Vegetation components have parameters like `rand_seed`, `tree_extra_y`, `tree_radius_high`, `tree_radius_low`, `tree_width`, `visual_color`, `visual_offset_x`, and `visual_offset_y` that influence their placement, size, and appearance.