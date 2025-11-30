---
title: Song Room Biome Configuration
category: biome
---

# Song Room Biome Configuration

This document details the configuration for the "Song Room" biome in Noita, focusing on its visual, structural, and auditory elements.

## Topology

The `Topology` element defines the fundamental structure and visual appearance of the biome.

### Key Attributes:

*   **`name`**: A descriptive name for the biome (currently "???").
*   **`type`**: Specifies the biome generation method, here `BIOME_WANG_TILE`, indicating it uses Wang tiles for generation.
*   **`background_use_neighbor`**: Controls whether the background image uses neighbor information for blending (0 means no).
*   **`background_image`**: Path to the main background image asset.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to edge assets for background image tiling.
*   **`background_edge_priority`**: Determines the rendering order of background edges.
*   **`wang_template_file`**: Path to the Wang tile template file (empty in this case, suggesting a default or script-driven generation).
*   **`lua_script`**: The primary script controlling biome generation and behavior (`data/scripts/biomes/song_room.lua`).
*   **`wang_map_width`, `wang_map_height`**: Dimensions of the generated biome map.
*   **`audio_music_2`**: Specifies the music track to play in this biome (`wandcave`).
*   **`audio_ambience`**: Specifies the ambient soundscape for this biome (`cave`).

### BitmapCaves:

This nested element controls the generation of cave structures within the biome.

*   **`size_x`, `size_y`**: Dimensions of the cave generation grid.
*   **`spawn_percent`**: Controls the density of cave spawning (0 means no random spawning).
*   **`blob_caves_count_min`, `blob_caves_count_max`**: Range for the number of large cave blobs.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: Range for the radius of these blobs.
*   **`blob_caves_strength_min`, `blob_caves_strength_max`**: Controls the "depth" or intensity of these blobs.
*   **`cave_childs_min`, `cave_childs_max`**: Range for the number of smaller cave systems branching off larger ones.
*   **`cave_count_min`, `cave_count_max`**: Range for the number of distinct cave systems.
*   **`cave_strength_min`, `cave_strength_max`**: Controls the intensity of general cave structures.
*   **`mountain_count_min`, `mountain_count_max`**: Range for the number of mountain-like structures (set to 0 here).

## Materials

The `Materials` element defines the types of materials that can appear within the biome and their distribution.

### Key Attributes:

*   **`name`**: A descriptive name for the material set (currently "???").

### MaterialComponent:

Each `MaterialComponent` defines a specific material and its properties within the biome.

| Attribute                 | Description