---
title: Orbroom 04 Biome Configuration
category: biome
---

# Orbroom 04 Biome Configuration

This document details the configuration for `orbroom_04.xml`, a biome definition file for Noita. It outlines the visual appearance, cave generation parameters, and material distribution for this specific orbroom variant.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's visual presentation and generation.

### Key Attributes:

*   **`name`**: `$biome_orbroom` - A reference name for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang tiles for generation.
*   **`background_use_neighbor`**: `0` - Disables background image blending with neighbors.
*   **`background_image`**: `data/weather_gfx/background_cave_09.png` - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Specifies edge graphics for the background image.
*   **`background_edge_priority`**: `11` - Determines the rendering order of background edges.
*   **`wang_template_file`**: `""` - No specific Wang template file is used, implying default or script-driven generation.
*   **`lua_script`**: `data/scripts/biomes/orbrooms/orbroom_04.lua` - The associated Lua script that controls biome generation and behavior.
*   **`wang_map_width`, `wang_map_height`**: `256` - The dimensions of the generated Wang map for this biome.
*   **`audio_music_2`**: `wandcave` - The music track to play in this biome.
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.

### BitmapCaves

This nested element controls the procedural generation of cave structures within the biome.

#### Key Attributes:

*   **`size_x`, `size_y`**: `256` - The dimensions of the bitmap used for cave generation.
*   **`spawn_percent`**: `0` - No specific percentage for spawning.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: `0`, `1` - Controls the number of "blob" caves.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: `1`, `1` - The radius of blob caves.
*   **`blob_caves_strength_min`, `blob_caves_strength_max`**: `1.2`, `2` - The strength or density of blob caves.
*   **`cave_childs_min`, `cave_childs_max`**: `0`, `1` - Controls the number of child caves.
*   **`cave_count_min`, `cave_count_max`**: `1`, `2` - The minimum and maximum number of main caves.
*   **`cave_strength_min`, `cave_strength_max`**: `0.2`, `1.8` - The strength or density of main caves.
*   **`mountain_count_min`, `mountain_count_max`**: `0`, `0` - No mountains are generated.
*   **`surface_caves_count_min`, `surface_caves_count_max`**: `0`, `0` - No surface caves are generated.

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome.

### Key Attributes:

*   **`name`**: `orbroom` - The name identifier for this material set.

### MaterialComponent

Each `<MaterialComponent>` defines a specific material and its properties within the biome.

#### MaterialComponent 1: `sand_static`

*   **`_enabled`**: `1` - This component is active.
*   **`is_rare`**: `0` - Not a rare material.
*   **`limit_max_y`**: `424.229` - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: `-1024` - Minimum Y-coordinate for this material.
*   **`limit_y`**: `1` - Y-axis limit for distribution.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`, `material_min`**: `0.55`, `0.45` - The maximum and minimum density of this material.
*   **`material_name`**: `sand_static` - The name of the material.
*   **`rare_use_polka`**: `1` - Uses polka noise for distribution.
*   **`rare_scale_x`, `rare_scale_y`**: `0.05`, `0.05` - Scale of the polka noise.

#### MaterialComponent 2: `diamond`

*   **`_enabled`**: `1` - This component is active.
*   **`is_rare`**: `1` - This is a rare material.
*   **`limit_max_y`**: `2048` - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: `100` - Minimum Y-coordinate for this material.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`, `material_min`**: `1.2`, `1.1` - The maximum and minimum density of this material.
*   **`material_name`**: `diamond` - The name of the material.
*   **`rare_polka_probability`**: `0.757143` - High probability for this rare material.
*   **`rare_scale_x`, `rare_scale_y`**: `0.0214286`, `0.0214286` - Scale of the polka noise.

#### MaterialComponent 3: `rock_hard`

*   **`_enabled`**: `1` - This component is active.
*   **`is_rare`**: `0` - Not a rare material.
*   **`limit_max_y`**: `2048` - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: `100` - Minimum Y-coordinate for this material.
*   **`material_index`**: `10` - Internal index for the material.
*   **`material_max`, `material_min`**: `1.0`, `0.6` - The maximum and minimum density of this material.
*   **`material_name`**: `rock_hard` - The name of the material.
*   **`add_perlin`**: `1` - Uses Perlin noise for distribution.
*   **`add_perlin_scale_y`, `add_perlin_scale_x`**: `0.01`, `0.01` - Scale of the Perlin noise.

#### MaterialComponent 4: `templebrickdark_static`

*   **`_enabled`**: `1` - This component is active.
*   **`is_rare`**: `0` - Not a rare material.
*   **`limit_max_y`**: `2048` - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: `100` - Minimum Y-coordinate for this material.
*   **`material_index`**: `11` - Internal index for the material.
*   **`material_max`, `material_min`**: `3.6`, `0.8` - The maximum and minimum density of this material.
*   **`material_name`**: `templebrickdark_static` - The name of the material.
*   **`add_perlin`**: `1` - Uses Perlin noise for distribution.
*   **`add_perlin_scale_y`, `add_perlin_scale_x`**: `0.01`, `0.01` - Scale of the Perlin noise.