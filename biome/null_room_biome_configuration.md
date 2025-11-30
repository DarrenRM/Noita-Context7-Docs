---
title: Null Room Biome Configuration
category: biome
---

# Null Room Biome Configuration

This document details the configuration for the "Null Room" biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental generation properties of the biome.

### Key Attributes:

*   **`name`**: "???" - The internal name for this biome topology.
*   **`type`**: "BIOME_WANG_TILE" - Indicates this biome uses Wang Tiles for generation.
*   **`background_use_neighbor`**: "0" - Disables background image blending with neighbors.
*   **`background_image`**: "data/weather_gfx/background_crypt.png" - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: "12" - Controls the rendering order of background edges.
*   **`wang_template_file`**: "" - No specific Wang template file is used, implying default or script-driven generation.
*   **`lua_script`**: "data/scripts/biomes/null_room.lua" - The Lua script responsible for custom biome generation logic.
*   **`wang_map_width`, `wang_map_height`**: "256" - Defines the dimensions of the generated biome map.
*   **`audio_music_2`**: "wandcave" - The music track associated with this biome.
*   **`audio_ambience`**: "cave" - The ambient soundscape for this biome.

### BitmapCaves Configuration:

This section controls the procedural generation of cave structures within the biome.

*   **`size_x`, `size_y`**: "256" - The dimensions of the bitmap used for cave generation.
*   **`spawn_percent`**: "0" - Indicates no direct spawning based on this percentage.
*   **`blob_caves_count_min/max`**: "0" to "1" - Controls the number of large cave blobs.
*   **`blob_caves_radius_min/max`**: "1" to "1" - Sets the radius of these blobs.
*   **`blob_caves_strength_min/max`**: "1.2" to "2" - Defines the intensity of blob cave generation.
*   **`cave_childs_min/max`**: "0" to "1" - Number of smaller cave systems branching from larger ones.
*   **`cave_count_min/max`**: "1" to "2" - The overall number of cave systems.
*   **`cave_strength_min/max`**: "0.2" to "1.8" - The intensity of general cave generation.
*   **`mountain_count_min/max`**: "0" to "0" - No mountains are generated.
*   **`surface_caves_count_min/max`**: "0" to "0" - No surface caves are generated.

## Materials

The `Materials` element defines the types and distribution of materials within the biome.

### MaterialComponent Breakdown:

Each `MaterialComponent` defines a specific material's properties and how it's placed.

| Attribute                 | Value