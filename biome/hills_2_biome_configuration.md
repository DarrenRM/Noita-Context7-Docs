---
title: Hills 2 Biome Configuration
category: biome
---

# Hills 2 Biome Configuration

This document details the configuration for the "Hills 2" biome in Noita, focusing on its topological generation, material distribution, and vegetation.

## Topology Generation

The `Topology` element defines the procedural generation of the biome's terrain.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base configuration.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/hills.lua` - Links to the Lua script that further defines biome behavior.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for terrain shaping.
*   **`mGradientAddNoise`**: `2` - Adds a noise component to the gradient for terrain variation.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `75.123` - Controls the intensity of noise at higher Y values.
*   **`mGradientLowNoise`**: `-12.0564` - Controls the intensity of noise at lower Y values.
*   **`mGradientNoiseScale`**: `0.0068571` - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.
*   **`mInsidePerlinScaleMax`**: `2` - Maximum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleMin`**: `0.057143` - Minimum scale for Perlin noise within the biome.
*   **`mMultiplierGradient`**: `0.871429` - A multiplier applied to the gradient for terrain shaping.
*   **`audio_ambience`**: `caves` - The primary ambient soundscape for this biome.
*   **`audio_ambience_surface`**: `hills` - The ambient soundscape for the surface layer of this biome.

### Bitmap Caves:

The `BitmapCaves` element defines parameters for generating cave structures using bitmap data.

*   **`name`**: `bitmap_hills` - Identifier for this cave generation configuration.
*   **`size_x`, `size_y`**: `512`, `256` - Dimensions of the bitmap used for cave generation.
*   **`blob_caves_count_min/max`**: `20`, `55` - Range for the number of "blob" caves.
*   **`blob_caves_radius_min/max`**: `1`, `10` - Range for the radius of blob caves.
*   **`cave_count_min/max`**: `50`, `100` - Range for the total number of caves.
*   **`cave_strength_min/max`**: `0.2`, `1` - Range for the strength of cave formations.
*   **`mountain_count_min/max`**: `0`, `15` - Range for the number of mountain-like formations.
*   **`surface_caves_count_min/max`**: `7`, `12` - Range for the number of caves specifically on the surface.

#### Structures:

Defines specific structures that can be placed within the caves.

| Attribute        | Description                                                              |
| :--------------- | :----------------------------------------------------------------------- |
| `image_file`     | Path to the image file defining the structure's shape.                   |
| `aabb_min_x/y`   | Minimum X/Y bounds for structure placement.                              |
| `aabb_max_x/y`   | Maximum X/Y bounds for structure placement.                              |
| `count_min/max`  | Minimum/maximum number of instances of this structure.                   |
| `strength_min/max` | Minimum/maximum strength (impact on terrain) of the structure.           |

**Example Structures:**

*   `cave_$[0-999].png`: General generated cave structures.
*   `mountain_rock.png`: Rock formations.
*   `skull_mountain.png`: Skull-shaped formations.
*   `eye.png`: Eye-shaped formations.
*   `pit.png`, `deep_pit.png`: Pit formations.
*   `brush_03.png` to `brush_06.png`: Various brush-like formations.

## Material Distribution

The `Materials` element governs the types and distribution of materials within the biome.

### Key Attributes:

*   **`name`**: `forest` - Identifier for this material set.

### Material Components:

Each `MaterialComponent` defines a specific material's properties and how it's placed.

| Attribute             | Description