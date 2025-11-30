---
title: Pyramid Right Biome Configuration
category: biome
---

# Pyramid Right Biome Configuration

This document details the configuration for the "Pyramid Right" biome in Noita, focusing on its topological generation, cave structures, and material distribution.

## Topology

The `Topology` element defines the fundamental shape and visual characteristics of the biome.

### Key Attributes:

*   **`name`**: `$biome_pyramid` - Internal identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_pyramid.png` - The main background texture.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Specifies edge textures for seamless background tiling.
*   **`background_edge_priority`**: `9` - Determines the rendering order of background edges.
*   **`lua_script`**: `data/scripts/biomes/pyramid_right.lua` - The associated Lua script for biome logic.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise used for terrain generation.
*   **Gradient Noise Parameters**: Controls the vertical distribution and intensity of noise for shaping the biome.
    *   `mGradientAddNoise`, `mGradientEndY`, `mGradientHighNoise`, `mGradientLowNoise`, `mGradientNoiseScale`, `mGradientStartY`
*   **Inside Noise Parameters**: Defines the noise used for internal cave structures and details.
    *   `mInsideNoiseFBM`, `mInsideNoiseType`, `mInsidePerlinClamped`, `mInsidePerlinScaleMax`, `mInsidePerlinScaleMin`, `mInsidePerlinScaleX`, `mInsidePerlinScaleY`, `mInsidePerlinScaled`, `mInsidePerlinSquared`, `mInsidePerlinForceInside`
*   **Multiplier Parameters**: Affects the overall intensity and appearance of the biome.
    *   `mMultiplierGradient`, `mMultiplierPerlin`
*   **`audio_ambience`**: `wandcave` - The primary ambient soundscape.
*   **`audio_ambience_surface`**: `desert` - Ambient soundscape for surface areas.
*   **`has_rain`**: `0` - Disables rain in this biome.

### Bitmap Caves:

This section defines the generation of cave systems within the biome.

*   **`size_x`, `size_y`**: Dimensions of the bitmap used for cave generation.
*   **`blob_caves_count_min/max`**: Minimum and maximum number of large cave blobs.
*   **`blob_caves_radius_min/max`**: Radius range for cave blobs.
*   **`blob_caves_strength_min/max`**: Strength range for cave blobs.
*   **`do_beginning_paths`**: `1` - Enables the generation of initial cave paths.
*   **`cave_childs_min/max`**: Number of smaller cave structures branching off main caves.
*   **`cave_count_min/max`**: Overall number of caves.
*   **`cave_strength_min/max`**: Strength range for general caves.
*   **`mountain_count_min/max`**: Controls the generation of mountain-like structures (set to 0 here).
*   **`surface_cave_childs_min/max`**: Number of cave structures near the surface.
*   **`surface_caves_count_min/max`**: Number of caves specifically on the surface.

#### Cave Structures:

These define specific pre-designed cave shapes that can be instantiated.

| Image File                     | AABB Min X | AABB Max X | AABB Min Y | AABB Max Y | Count Min | Count Max | Strength Min | Strength Max |
| :----------------------------- | :--------- | :--------- | :--------- | :--------- | :-------- | :-------- | :----------- | :----------- |
| `data/biome_impl/caves/pit.png` | 5          | 507        | -8         | 2          | 2         | 5         | 0.0          | 0.65         |
| `data/biome_impl/caves/deep_pit.png` | 5          | 507        | -8         | 2          | 5         | 8         | 0.0          | 0.40         |
| `data/biome_impl/caves/brush_03.png` | 5          | 507        | 0          | 15         | 0         | 3         | 1.15         | 1.85         |
| `data/biome_impl/caves/brush_04.png` | 5          | 507        | 0          | 15         | 0         | 4         | 0.5          | 2.85         |
| `data/biome_impl/caves/brush_05.png` | 5          | 507        | 0          | 25         | 0         | 3         | 0.15         | 2.15         |
| `data/biome_impl/caves/brush_06.png` | 5          | 507        | 0          | 35         | 0         | 4         | 0.55         | 1.85         |

## Materials

The `Materials` section defines the distribution and properties of different in-game materials within the biome.

### Key Attributes:

*   **`name`**: `forest` - This seems to be a naming convention for the material group, though the biome is "Pyramid Right".

#### Material Components:

Each `MaterialComponent` defines a specific material's presence and behavior.

| Material Name        | Limit Min Y | Limit Max Y | Material Min | Material Max | Is Rare | Use Polka | Use Perlin | Polka Probability |
| :------------------- | :---------- | :---------- | :----------- | :----------- | :------ | :-------- | :--------- | :---------------- |
| `sand_surface`       | -1024       | 424.229     | 0.45         | 0.51         | 0       | 1         | 0          | 0.2               |
| `sandstone_surface`  | -1024       | 424.229     | 0.5          | 0.6          | 0       | 1         | 0          | 0.2               |
| `sand_static_bright` | -1024       | 600         | 0.59         | 0.73         | 0       | 0         | 0          | -                 |
| `sand_static`        | -1024       | 700         | 0.72         | 0.95         | 0       | 0         | 0          | -                 |
| `copper`             | 750         | 2048        | 1.05         | 1.25         | 1       | 1         | 1          | 0.357143          |
| `rock_static`        | 100         | 2048        | 0.9          | 3.5          | 0       | 0         | 0          | -                 |

**Summary of Material Distribution:**

*   **Lower Y-levels (-1024 to ~700):** Dominated by various sand and sandstone types, with `sand_static_bright` and `sand_static` appearing at higher Y-levels within this range.
*   **Mid to Upper Y-levels (100 to 2048):** `rock_static` is prevalent.
*   **Specific Upper Y-levels (750 to 2048):** `copper` appears as a rare material, with specific polka and perlin noise settings for its distribution.

**Note:** The `limit_y="1"` or `limit_y="0"` attributes on `MaterialComponent` likely control whether the material is placed on the surface or within the terrain, respectively.