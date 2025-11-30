---
title: Secret Altar Biome Configuration
category: biome
---

# Secret Altar Biome Configuration

This document details the configuration for the "Secret Altar" biome in Noita, focusing on its generation and material composition.

## Topology

The `Topology` element defines the fundamental structure and generation parameters for the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies that this biome uses Wang tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - Sets the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/secret_altar.lua` - The associated Lua script that controls biome-specific logic.
*   **`wang_map_width`**: `256` - The width of the generated Wang tile map.
*   **`wang_map_height`**: `256` - The height of the generated Wang tile map.

### Bitmap Caves Generation:

The `BitmapCaves` element controls the procedural generation of cave structures within the biome.

*   **`size_x`**, **`size_y`**: `256` - Dimensions for cave generation.
*   **`spawn_percent`**: `0` - No specific spawn percentage for caves.
*   **`blob_caves_count_min`/`max`**: `0`/`1` - Controls the number of large blob-like cave formations.
*   **`blob_caves_radius_min`/`max`**: `1`/`1` - Defines the radius of these blob caves.
*   **`cave_count_min`/`max`**: `1`/`2` - The number of standard cave systems to generate.
*   **`cave_strength_min`/`max`**: `0.2`/`1.8` - Controls the density and complexity of cave structures.
*   **`mountain_count_min`/`max`**: `0`/`0` - No mountains are generated in this biome.
*   **`surface_caves_count_min`/`max`**: `0`/`0` - No surface caves are generated.

## Materials

The `Materials` element defines the distribution and properties of different materials within the biome. Each `MaterialComponent` specifies how a particular material is placed and its characteristics.

### Key Material Components:

| Attribute                 | Description