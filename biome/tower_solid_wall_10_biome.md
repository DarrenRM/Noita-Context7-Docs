---
title: Tower Solid Wall 10 Biome
category: biome
---

# Tower Solid Wall 10 Biome

This document describes the configuration for a specific biome in Noita, identified as "Tower Solid Wall 10". It defines the visual and structural properties of this area, including its background, cave generation, and material composition.

## Topology

The `<Topology>` element defines the overall structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: "???" - The internal name for this biome topology.
*   **`type`**: "BIOME_WANG_TILE" - Indicates this biome uses Wang tiles for generation.
*   **`background_use_neighbor`**: "0" - Disables background blending with neighboring biomes.
*   **`background_image`**: "data/weather_gfx/background_crypt.png" - Specifies the main background image.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: "110" - Determines the rendering order of background edges.
*   **`lua_script`**: "data/scripts/biomes/tower_end.lua" - The Lua script that governs the biome's behavior and generation logic.
*   **`wang_map_width`, `wang_map_height`**: "256" - Dimensions of the Wang map used for generation.
*   **`audio_music_2`**: "tower" - The music track associated with this biome.
*   **`audio_ambience`**: "cave" - The ambient soundscape for this biome.

### BitmapCaves:

This nested element controls the generation of cave-like structures within the biome.

*   **`size_x`, `size_y`**: "256" - The dimensions of the bitmap used for cave generation.
*   **`spawn_percent`**: "0" - No random spawning of cave elements based on percentage.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: "0" to "1" - Controls the number of blob-like cave formations.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: "1" to "2" - Defines the size range of blob caves.
*   **`blob_caves_strength_min`, `blob_caves_strength_max`**: "1.2" to "2" - Controls the density or "strength" of blob caves.
*   **`cave_childs_min`, `cave_childs_max`**: "0" to "1" - Number of smaller caves that can branch off larger ones.
*   **`cave_count_min`, `cave_count_max`**: "1" to "2" - The total number of main caves to generate.
*   **`cave_strength_min`, `cave_strength_max`**: "0.2" to "1.8" - Controls the density or "strength" of main caves.
*   **`mountain_count_min`, `mountain_count_max`**: "0" - No mountains are generated in this biome.

## Materials

The `<Materials>` element defines the types and distribution of materials that make up the biome's terrain.

### Key Attributes:

*   **`name`**: "???" - The internal name for this material set.

### MaterialComponent:

Each `<MaterialComponent>` defines a specific material and its properties within the biome.

| Attribute                 | Value