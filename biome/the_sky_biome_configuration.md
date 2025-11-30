---
title: The Sky Biome Configuration
category: biome
---

---

# The Sky Biome Configuration

This document details the configuration for "The Sky" biome in Noita, focusing on its generation and material properties.

## Topology

The `Topology` element defines the fundamental structure and generation parameters of the biome.

### Key Attributes:

*   **`name`**: `$biome_boss_victoryroom` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for generation.
*   **`wang_template_file`**: `data/wang_tiles/the_sky.png` - Specifies the image file used for Wang Tile generation.
*   **`lua_script`**: `data/scripts/biomes/the_end.lua` - The associated Lua script that can influence biome behavior.
*   **`wang_map_width` / `wang_map_height`**: `256` - Dimensions of the Wang map.
*   **`coarse_map_not_terrain`**: `1` - Suggests this biome's coarse map doesn't directly represent terrain.
*   **`coarse_map_cell_count_always_zero`**: `1` - Indicates cells in the coarse map always have a count of zero.
*   **`audio_ambience`**: `snowcave` - The ambient soundscape for this biome.
*   **`audio_music_2`**: `the_end` - The music track associated with this biome.

### BitmapCaves:

This section controls the generation of cave-like structures within the biome.

*   **`size_x` / `size_y`**: `512` / `256` - Dimensions for bitmap cave generation.
*   **`blob_caves_count_min` / `blob_caves_count_max`**: `0` - No blob caves are generated.
*   **`cave_childs_min` / `cave_childs_max`**: `0` / `1` - Controls the number of child caves.
*   **`cave_count_min` / `cave_count_max`**: `2` - Exactly two main caves are generated.
*   **`cave_strength_min` / `cave_strength_max`**: `0.2` / `1` - Defines the strength/density of caves.
*   **`mountain_count_min` / `mountain_count_max`**: `0` - No mountains are generated.
*   **`surface_caves_count_min` / `surface_caves_count_max`**: `0` - No surface caves are generated.
*   **`spawn_percent`**: `0` - No specific spawn percentage for caves.

## Materials

The `Materials` element defines the different materials present in the biome and their properties.

### Key Material Components:

The `MaterialComponent` elements describe how specific materials are distributed and their characteristics.

#### Material: `snow` (Rare)

*   **`is_rare`**: `1` - This is a rare variant of snow.
*   **`limit_max_y`**: `2048` - Maximum Y-level for this material.
*   **`limit_min_y`**: `100` - Minimum Y-level for this material.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max` / `material_min`**: `0.55` / `0.51` - Density range for this material.
*   **`rare_polka_is_boxed`**: `0` - Polka distribution is not boxed.
*   **`rare_polka_probability`**: `0.160871` - Probability of polka distribution.
*   **`rare_polka_radius_high` / `low`**: `0.771429` / `0.357143` - Radius for polka distribution.
*   **`rare_scale_x` / `y`**: `0.0100004` / `0.00357165` - Scaling for the texture.
*   **`rare_use_polka`**: `1` - Uses polka distribution.

#### Material: `cloud` (Standard)

*   **`is_rare`**: `0` - This is a standard, non-rare material.
*   **`limit_max_y`**: `2048` - Maximum Y-level.
*   **`limit_min_y`**: `100` - Minimum Y-level.
*   **`material_index`**: `10` - Internal index.
*   **`material_max` / `material_min`**: `1.55` / `0.53` - Density range.

#### Material: `snow` (Rare, Boxed Polka)

*   **`is_rare`**: `1` - Rare variant of snow.
*   **`limit_max_y`**: `2048` - Maximum Y-level.
*   **`limit_min_y`**: `100` - Minimum Y-level.
*   **`material_index`**: `10` - Internal index.
*   **`material_max` / `material_min`**: `1.2` / `1.1` - Density range.
*   **`rare_polka_is_boxed`**: `1` - Polka distribution is boxed.
*   **`rare_polka_probability`**: `0.157143` - Probability of polka distribution.
*   **`rare_polka_radius_high` / `low`**: `0.464286` / `0.0428571` - Radius for polka distribution.
*   **`rare_required_min`**: `0.371429` - Minimum requirement for this material.
*   **`rare_scale_x` / `y`**: `0.0214286` - Scaling for the texture.
*   **`rare_use_perlin`**: `1` - Uses Perlin noise for distribution.
*   **`rare_use_polka`**: `1` - Uses polka distribution.

#### Material: `snow` (Rare, Higher Y-level)

*   **`is_rare`**: `1` - Rare variant of snow.
*   **`limit_max_y`**: `2048` - Maximum Y-level.
*   **`limit_min_y`**: `750` - Higher minimum Y-level for this variant.
*   **`material_index`**: `9` - Internal index.
*   **`material_max` / `material_min`**: `1.2` / `1.05` - Density range.
*   **`rare_polka_is_boxed`**: `0` - Polka distribution is not boxed.
*   **`rare_polka_probability`**: `0.357143` - Probability of polka distribution.
*   **`rare_polka_radius_high` / `low`**: `0.564286` / `0.328571` - Radius for polka distribution.
*   **`rare_required_min`**: `0.019` - Minimum requirement.
*   **`rare_scale_x` / `y`**: `0.027514286` / `0.057514286` - Scaling for the texture.
*   **`rare_use_perlin`**: `1` - Uses Perlin noise.
*   **`rare_use_polka`**: `1` - Uses polka distribution.

#### Material: `cloud_lighter` (Standard)

*   **`is_rare`**: `0` - Standard material.
*   **`limit_max_y`**: `2048` - Maximum Y-level.
*   **`limit_min_y`**: `100` - Minimum Y-level.
*   **`material_index`**: `9` - Internal index.
*   **`material_max` / `material_min`**: `3.5` / `0.8` - Density range.
*   **`add_perlin`**: `1` - Adds Perlin noise for variation.
*   **`add_perlin_scale_y` / `x`**: `0.02` / `0.01` - Scaling for the added Perlin noise.