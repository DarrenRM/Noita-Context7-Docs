---
title: Ending Placeholder Biome Configuration
category: biome
---

# Ending Placeholder Biome Configuration

This document details the configuration for the `ending_placeholder.xml` biome file, which serves as a template or placeholder for end-game biomes. It defines the topological generation, material distribution, and visual elements of the biome.

## Topology

The `<Topology>` element defines the fundamental structure and generation parameters of the biome.

### Key Attributes:

*   **`name`**: `$biome_ending_placeholder` - The internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates that this biome uses Wang Tiles for its generation.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - Specifies the background image used for this biome.
*   **`lua_script`**: `data/scripts/biomes/ending_placeholder.lua` - The Lua script that controls dynamic behavior and generation logic for this biome.
*   **`wang_map_width` / `wang_map_height`**: `256` - The dimensions of the Wang map used for generation.
*   **`audio_music_2`**: `boss01` - The music track to play in this biome (likely a boss theme).
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.

### BitmapCaves

This nested element controls the procedural generation of caves within the biome.

#### Key Attributes:

*   **`size_x` / `size_y`**: `256` - The size of the bitmap used for cave generation.
*   **`spawn_percent`**: `0` - Indicates no direct spawning based on this percentage.
*   **`blob_caves_count_min` / `max`**: `0` / `1` - Controls the number of large cave blobs.
*   **`blob_caves_radius_min` / `max`**: `1` - Defines the radius of these blobs.
*   **`cave_count_min` / `max`**: `1` / `2` - The number of smaller caves to generate.
*   **`cave_strength_min` / `max`**: `0.2` / `1.8` - Controls the density and prominence of caves.
*   **`mountain_count_min` / `max`**: `0` / `0` - Explicitly disables mountain generation.

## Materials

The `<Materials>` element defines the types of materials present in the biome and their distribution.

### Key Attributes:

*   **`name`**: `crypt` - A logical grouping name for these material definitions.

### MaterialComponent

Each `<MaterialComponent>` defines a specific material and its properties within the biome.

#### Key Material Components:

*   **`sand_static`**:
    *   `material_name`: `sand_static`
    *   `material_min` / `max`: `0.45` / `0.55` - The base density range.
    *   `limit_max_y`: `424.229` - Upper vertical limit for this material.
    *   `rare_use_polka`: `1` - Enables a polka-dot distribution pattern for rare occurrences.
    *   `rare_polka_probability`: `0.2` - The chance of a rare polka-dot pattern appearing.

*   **`diamond`**:
    *   `material_name`: `diamond`
    *   `is_rare`: `1` - This material is considered rare.
    *   `material_min` / `max`: `1.1` / `1.2` - Higher density for rare materials.
    *   `limit_min_y`: `100` - Minimum vertical spawn height.
    *   `rare_polka_probability`: `0.757143` - High probability for rare diamond distribution.

*   **`rock_hard`**:
    *   `material_name`: `rock_hard`
    *   `material_min` / `max`: `0.6` / `1.0` - Standard density range.
    *   `add_perlin`: `1` - Adds Perlin noise for a more natural, varied texture.
    *   `add_perlin_scale_y` / `x`: `0.01` - Controls the scale of the Perlin noise.

*   **`templebrickdark_static`**:
    *   `material_name`: `templebrickdark_static`
    *   `material_min` / `max`: `0.8` / `3.6` - Wide density range.
    *   `add_perlin`: `1` - Uses Perlin noise for texture variation.

### VegetationComponent

These components define decorative elements and flora within the biome.

#### Key Vegetation Components:

*   **Vine Growth**:
    *   `tree_image_file`: `data/vegetation/vine_growth_1.xml`
    *   `tree_material`: `ceiling_plant_material`
    *   `tree_probability`: `0.24571`
    *   `is_ceiling_plant`: `1` - Indicates this vegetation grows from the ceiling.

*   **Ceiling Vegetation**:
    *   `tree_image_file`: `data/vegetation/ceiling_vegetation_00$[2-8].png` - Uses a pattern for varied images.
    *   `tree_material`: `ceiling_plant_material`
    *   `tree_probability`: `0.54571`
    *   `is_ceiling_plant`: `1` - Also grows from the ceiling.

---