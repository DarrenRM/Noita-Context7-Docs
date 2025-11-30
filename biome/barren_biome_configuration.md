---
title: Barren Biome Configuration
category: biome
---

# Barren Biome Configuration

This document details the configuration for the "Barren" biome in Noita, focusing on its visual and environmental properties.

## Topology

The `<Topology>` element defines the core characteristics of the biome's structure and appearance.

### Key Attributes:

*   **`name`**: `$biome_barren` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang tiles for generation.
*   **`static_tile`**: `1` - Marks this as a static tile biome, meaning its layout is pre-defined or generated from a static template.
*   **`static_tile_bg_mask`**: `data/biome_impl/static_tile/temples-assets/barren_bg.png` - Path to the background mask image used for static tile generation.
*   **`background_image`**: `data/weather_gfx/background_wandcave.png` - The primary background image for the biome.
*   **`wang_template_file`**: `data/biome_impl/static_tile/temples-assets/barren_fg.png` - The foreground Wang tile template image.
*   **`lua_script`**: `data/biome_impl/static_tile/temples_common.lua` - A Lua script that can influence biome generation or behavior.
*   **`wang_map_width` / `wang_map_height`**: `153` / `94` - Dimensions of the Wang map.
*   **`audio_ambience`**: `temple` - The ambient soundscape for this biome.
*   **`audio_music_2`**: `barren` - The music track associated with this biome.
*   **`rain_target_mod`**: `0.25` - Modifies the intensity of rain.
*   **`fog_target_mod`**: `0.25` - Modifies the intensity of fog.

### BitmapCaves:

This section defines parameters for generating cave-like structures within the biome.

*   **`size_x` / `size_y`**: `516` / `256` - Dimensions for cave generation.
*   **`blob_caves_count_min` / `blob_caves_count_max`**: `0` / `1` - Controls the number of blob-like cave formations.
*   **`cave_count_min` / `cave_count_max`**: `1` / `2` - Controls the number of standard cave formations.
*   **`cave_strength_min` / `cave_strength_max`**: `0.2` / `1.8` - Influences the intensity or depth of caves.

## Materials

The `<Materials>` element defines the various materials and vegetation that can spawn within the biome.

### Material Components:

These define the properties of different materials that make up the biome's terrain.

| Material Name                     | `is_rare` | `material_index` | `material_max` | `material_min` | `rare_polka_probability` | `rare_scale_x` | `rare_scale_y` |
| :-------------------------------- | :-------- | :--------------- | :------------- | :------------- | :----------------------- | :------------- | :------------- |
| `diamond`                         | `1`       | `10`             | `1.2`          | `1.1`          | `0.757143`               | `0.0214286`    | `0.0214286`    |
| `snow`                            | `1`       | `10`             | `1.3`          | `1.0`          | `0.3`                    | `0.01`         | `0.04`         |
| `templeslab_crumbling_static`     | `0`       | `11`             | `3.5`          | `0.00006`      | `0.2`                    | `0.05`         | `0.05`         |

*   **`is_rare`**: Indicates if the material is considered rare.
*   **`material_index`**: An internal index for the material.
*   **`material_max` / `material_min`**: Defines the range for the material's density or presence.
*   **`rare_polka_probability`**: Controls the probability of a "polka" pattern for rare materials.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling factors for the rare material's distribution.

### Vegetation Components:

These define the types of vegetation that can appear in the biome.

| Component Type      | `_enabled` | `is_visual` | `tree_image_file`                               | `tree_material`          | `tree_probability` | `tree_radius_high` | `tree_radius_low` | `is_ceiling_plant` |
| :------------------ | :--------- | :---------- | :---------------------------------------------- | :----------------------- | :----------------- | :----------------- | :---------------- | :----------------- |
| Ceiling Vegetation  | `1`        | `1`         | `data/vegetation/vine_growth_1.xml`             | `ceiling_plant_material` | `0.24571`          | `0.635286`         | `0.146757`        | `1`                |
| Ceiling Vegetation  | `1`        | `1`         | `data/vegetation/ceiling_vegetation_00$[2-8].png` | `ceiling_plant_material` | `0.54571`          | `0.635286`         | `0.146757`        | `1`                |

*   **`_enabled`**: Whether this vegetation component is active.
*   **`is_visual`**: If this is purely a visual element.
*   **`tree_image_file`**: Path to the image or sprite for the vegetation.
*   **`tree_material`**: The material associated with this vegetation.
*   **`tree_probability`**: The chance of this vegetation spawning.
*   **`tree_radius_high` / `tree_radius_low`**: Defines the radial distribution of the vegetation.
*   **`is_ceiling_plant`**: Indicates if the vegetation grows from the ceiling.