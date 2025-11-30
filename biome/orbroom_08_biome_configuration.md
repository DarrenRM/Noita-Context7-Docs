---
title: Orbroom 08 Biome Configuration
category: biome
---

# Orbroom 08 Biome Configuration

This document details the configuration for `orbroom_08.xml`, a biome definition within Noita. It focuses on the visual and structural aspects of this specific orbroom variant.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's layout and appearance.

### Key Attributes:

*   **`name`**: `$biome_orbroom` - A reference name for this biome type.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_the_end.png` - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Specifies edge graphics for the background, creating seamless transitions.
*   **`background_edge_priority`**: `11` - Determines the rendering order of background edges.
*   **`lua_script`**: `data/scripts/biomes/orbrooms/orbroom_08.lua` - The associated Lua script that controls dynamic behavior and entity spawning within this biome.
*   **`wang_map_width`, `wang_map_height`**: `256` - The dimensions of the Wang Tile map used for generation.
*   **`audio_music_2`**: `wandcave` - The music track associated with this biome.
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.

### BitmapCaves

This nested element controls the procedural generation of cave structures within the biome.

#### Key Attributes:

*   **`size_x`, `size_y`**: `256` - The dimensions of the bitmap used for cave generation.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: `0` to `1` - Controls the number of large "blob" caves.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: `1` to `1` - Defines the radius of these blob caves.
*   **`cave_count_min`, `cave_count_max`**: `1` to `2` - The number of standard caves to generate.
*   **`cave_strength_min`, `cave_strength_max`**: `0.2` to `1.8` - The intensity or density of cave generation.
*   **`mountain_count_min`, `mountain_count_max`**: `0` to `0` - No mountains are generated in this biome.

## Materials

The `<Materials>` element defines the different material components that make up the biome's terrain and their distribution.

### MaterialComponent

Each `<MaterialComponent>` defines a specific material and its properties within the biome.

#### Key Attributes:

*   **`material_name`**: The name of the material (e.g., `sand_static`, `diamond`, `rock_hard`, `templebrickdark_static`).
*   **`material_index`**: An internal index for the material.
*   **`is_rare`**: `0` or `1` - Indicates if the material is considered rare.
*   **`limit_max_y`, `limit_min_y`**: Vertical boundaries for where the material can appear.
*   **`material_min`, `material_max`**: The minimum and maximum density or prevalence of the material.
*   **`rare_use_polka`**: `1` - Indicates that a polka-like distribution pattern is used for rare materials.
*   **`rare_polka_probability`**: The probability of the material appearing in a polka pattern.
*   **`rare_polka_radius_low`, `rare_polka_radius_high`**: The range of radii for the polka distribution.
*   **`rare_required_min`, `rare_required_max`**: Minimum and maximum requirements for the material to be placed.
*   **`rare_scale_x`, `rare_scale_y`**: Scaling factors for the rare material's distribution.
*   **`add_perlin`**: `1` - Indicates Perlin noise is used to add variation to the material's placement.
*   **`add_perlin_scale_y`, `add_perlin_scale_x`**: Scaling factors for the Perlin noise.

#### Material Breakdown:

| Material Name           | `is_rare` | `limit_max_y` | `limit_min_y` | `material_min` | `material_max` | `rare_use_polka` | `add_perlin` |
| :---------------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :--------------- | :----------- |
| `sand_static`           | 0         | 424.229       | -1024         | 0.45           | 0.55           | 1                | 0            |
| `diamond`               | 1         | 2048          | 100           | 1.1            | 1.2            | 1                | 0            |
| `rock_hard`             | 0         | 2048          | 100           | 0.6            | 1.0            | 1                | 1            |
| `templebrickdark_static`| 0         | 2048          | 100           | 0.8            | 3.6            | 1                | 1            |