---
title: Magic Gate Biome Configuration
category: biome
---

---

# Magic Gate Biome Configuration

This document details the configuration for the "Magic Gate" biome in Noita, focusing on its generation and material composition.

## Topology

The `Topology` element defines the fundamental structure and generation parameters of the biome.

### Key Attributes:

*   **`name`**: `$biome_magic_gate` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_the_end.png` - Specifies the background visual.
*   **`wang_template_file`**: `data/wang_tiles/the_end.png` - Points to the Wang Tile image used for generation.
*   **`lua_script`**: `data/scripts/biomes/magic_gate.lua` - The associated Lua script for biome-specific logic.
*   **`wang_map_width` / `wang_map_height`**: `256` - Dimensions of the generated biome map.

### BitmapCaves

This section controls the generation of cave structures within the biome.

*   **`size_x` / `size_y`**: `516` / `256` - Dimensions for bitmap cave generation.
*   **`spawn_percent`**: `0` - Caves do not spawn based on a percentage.
*   **`blob_caves_count_min/max`**: `0` / `1` - Controls the number of large blob-like cave formations.
*   **`blob_caves_radius_min/max`**: `1` / `1` - Defines the radius of these blob caves.
*   **`cave_count_min/max`**: `1` / `2` - The number of standard cave systems.
*   **`cave_strength_min/max`**: `0.2` / `1.8` - Influences the density and complexity of cave structures.
*   **`mountain_count_min/max`**: `0` / `0` - No mountains are generated in this biome.
*   **`surface_caves_count_min/max`**: `0` / `0` - No surface caves are generated.

## Materials

The `Materials` section defines the distribution and properties of various materials within the biome.

### MaterialComponent

Each `MaterialComponent` defines a specific material's presence and characteristics.

| Attribute Name           | Description