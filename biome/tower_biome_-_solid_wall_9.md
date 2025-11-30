---
title: Tower Biome - Solid Wall 9
category: biome
---

# Tower Biome - Solid Wall 9

This document describes the configuration for a specific Tower biome variant in Noita, focusing on its environmental properties and material distribution.

## Topology

The `Topology` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `$biome_tower` - A reference name for this biome type.
*   **`type`**: `BIOME_WANG_TILE` - Indicates that this biome uses Wang tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_the_end.png` - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Specifies edge graphics for the background, creating seamless transitions.
*   **`background_edge_priority`**: `109` - Determines the rendering order of background edges.
*   **`wang_template_file`**: `data/wang_tiles/the_end.png` - The image file containing the Wang tile patterns used for terrain generation.
*   **`lua_script`**: `data/scripts/biomes/tower.lua` - The Lua script that controls biome-specific behaviors and generation logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - Dimensions of the Wang tile map used for generation.
*   **`audio_music_2`**: `tower` - The music track associated with this biome.
*   **`audio_ambience`**: `snowcave` - The ambient soundscape for this biome.

### BitmapCaves:

This section defines parameters for generating cave structures within the biome.

*   **`size_x`, `size_y`**: `512`, `256` - Dimensions of the bitmap used for cave generation.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: `0`, `0` - No blob caves are generated.
*   **`cave_childs_min`, `cave_childs_max`**: `0`, `1` - Allows for a small number of child caves.
*   **`cave_count_min`, `cave_count_max`**: `2`, `2` - Exactly two main cave structures are generated.
*   **`cave_strength_min`, `cave_strength_max`**: `0.2`, `1` - Controls the intensity or size of generated caves.
*   **`mountain_count_min`, `mountain_count_max`**: `0`, `0` - No mountains are generated.
*   **`surface_caves_count_min`, `surface_caves_count_max`**: `0`, `0` - No surface caves are generated.
*   **`spawn_percent`**: `0` - No specific spawn percentage for caves.

## Materials

The `Materials` element defines the distribution and properties of various materials within the biome.

### Material Components:

Each `MaterialComponent` defines a specific material and its generation parameters.

*   **`coal` (Rare)**:
    *   `is_rare`: `1`
    *   `limit_max_y`: `2048`
    *   `limit_min_y`: `100`
    *   `material_max`: `0.55`
    *   `material_min`: `0.51`
    *   `rare_polka_probability`: `0.160871`
    *   `rare_polka_radius_high`: `0.771429`
    *   `rare_polka_radius_low`: `0.357143`
    *   `rare_scale_x`: `0.0100004`
    *   `rare_scale_y`: `0.00357165`
    *   `rare_use_polka`: `1`

*   **`skullrock` (Common)**:
    *   `is_rare`: `0`
    *   `limit_max_y`: `2048`
    *   `limit_min_y`: `100`
    *   `material_max`: `1.55`
    *   `material_min`: `0.53`

*   **`coal` (Rare, Boxed)**:
    *   `is_rare`: `1`
    *   `limit_max_y`: `2048`
    *   `limit_min_y`: `100`
    *   `material_max`: `1.2`
    *   `material_min`: `1.1`
    *   `rare_polka_is_boxed`: `1`
    *   `rare_polka_probability`: `0.157143`
    *   `rare_polka_radius_high`: `0.464286`
    *   `rare_polka_radius_low`: `0.0428571`
    *   `rare_required_min`: `0.371429`
    *   `rare_scale_x`: `0.0214286`
    *   `rare_scale_y`: `0.0214286`
    *   `rare_use_perlin`: `1`
    *   `rare_use_polka`: `1`

*   **`lava` (Rare)**:
    *   `is_rare`: `1`
    *   `limit_max_y`: `2048`
    *   `limit_min_y`: `750`
    *   `material_max`: `1.2`
    *   `material_min`: `1.05`
    *   `rare_polka_probability`: `0.357143`
    *   `rare_polka_radius_high`: `0.564286`
    *   `rare_polka_radius_low`: `0.328571`
    *   `rare_required_min`: `0.019`
    *   `rare_scale_x`: `0.027514286`
    *   `rare_scale_y`: `0.057514286`
    *   `rare_use_perlin`: `1`
    *   `rare_use_polka`: `1`

*   **`the_end` (Common)**:
    *   `is_rare`: `0`
    *   `limit_max_y`: `2048`
    *   `limit_min_y`: `100`
    *   `material_max`: `3.5`
    *   `material_min`: `0.8`
    *   `add_perlin`: `1`
    *   `add_perlin_scale_y`: `0.02`
    *   `add_perlin_scale_x`: `0.01`

### Vegetation Component:

*   **`redplant_0$[1-4]`**:
    *   `is_visual`: `1`
    *   `tree_extra_y`: `-1`
    *   `tree_image_file`: `data/vegetation/redplant_0$[1-4].xml`
    *   `tree_material`: `plant_material_red`
    *   `tree_probability`: `0.528571`
    *   `tree_radius_high`: `0.214286`
    *   `tree_radius_low`: `0.1027`
    *   `tree_width`: `30.571`
    *   `visual_color`: `0xff4d5d44`
    *   `visual_offset_x`: `15`
    *   `visual_offset_y`: `32`