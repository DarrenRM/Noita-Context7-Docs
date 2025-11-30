---
title: Greed Room Biome Configuration
category: biome
---

---

# Greed Room Biome Configuration

This document details the configuration for the "Greed Room" biome in Noita, focusing on its visual and structural properties.

## Topology

The `Topology` element defines the fundamental layout and visual aspects of the biome.

### Key Attributes:

*   **`name`**: `$biome_greed_room` - Internal identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang tiles for generation.
*   **`background_use_neighbor`**: `0` - Disables background blending with adjacent biomes.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - Specifies the main background texture.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to edge graphics for the background.
*   **`background_edge_priority`**: `12` - Determines the rendering order of background edges.
*   **`lua_script`**: `data/scripts/biomes/greed_room.lua` - Links to the biome's scripting logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - Dimensions of the Wang tile map used for generation.
*   **`audio_music_2`**: `wandcave` - Specifies the music track for this biome.
*   **`audio_ambience`**: `cave` - Sets the ambient soundscape.

### BitmapCaves

This section controls the procedural generation of cave structures within the biome.

*   **`size_x`, `size_y`**: `256` - Dimensions of the area for cave generation.
*   **`spawn_percent`**: `0` - No specific percentage for spawning.
*   **`blob_caves_count_min/max`**: `0`/`1` - Controls the number of large cave blobs.
*   **`blob_caves_radius_min/max`**: `1`/`1` - Defines the radius of these blobs.
*   **`blob_caves_strength_min/max`**: `1.2`/`2` - Affects the intensity/density of blob caves.
*   **`cave_childs_min/max`**: `0`/`1` - Number of smaller cave systems branching off.
*   **`cave_count_min/max`**: `1`/`2` - Total number of main cave systems.
*   **`cave_strength_min/max`**: `0.2`/`1.8` - Controls the density and complexity of caves.
*   **`mountain_count_min/max`**: `0`/`0` - No mountains are generated in this biome.

## Materials

The `Materials` element defines the types and distribution of materials that form the biome's terrain.

### Material Components

Each `MaterialComponent` defines a specific material and its properties within the biome.

| Attribute                 | Description