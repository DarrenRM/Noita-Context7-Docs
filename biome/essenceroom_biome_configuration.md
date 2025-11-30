---
title: Essenceroom Biome Configuration
category: biome
---

---

# Essenceroom Biome Configuration

This document details the configuration for the "Essenceroom" biome in Noita, focusing on its visual and structural properties.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for its generation.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - Specifies the main background image for the biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: These define the edge graphics for the background, ensuring seamless transitions.
*   **`background_edge_priority`**: `12` - Controls the layering and rendering order of background elements.
*   **`lua_script`**: `data/scripts/biomes/essenceroom.lua` - Links to the script that governs the biome's dynamic behavior and generation logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - Defines the dimensions of the Wang map used for biome generation.
*   **`audio_music_2`**: `wandcave` - Sets the primary music track for this biome.
*   **`audio_ambience`**: `cave` - Specifies the ambient soundscape for the biome.

### BitmapCaves:

This section controls the procedural generation of cave structures within the biome.

*   **`size_x`, `size_y`**: `256` - The dimensions of the bitmap used for cave generation.
*   **`spawn_percent`**: `0` - Indicates no direct spawning based on this percentage.
*   **`blob_caves_count_min/max`**: `0` to `1` - Controls the number of large "blob" cave formations.
*   **`blob_caves_radius_min/max`**: `1` - Sets the radius for these blob caves.
*   **`cave_childs_min/max`**: `0` to `1` - Determines the number of smaller cave systems branching off main ones.
*   **`cave_count_min/max`**: `1` to `2` - Controls the overall number of distinct cave systems.
*   **`cave_strength_min/max`**: `0.2` to `1.8` - Influences the density and complexity of cave generation.
*   **`mountain_count_min/max`**: `0` to `0` - Explicitly disables mountain generation within this biome.

## Materials

The `Materials` element defines the types and distribution of materials found within the biome.

### Material Components:

Each `MaterialComponent` defines a specific material and its properties.

| Attribute                 | Description