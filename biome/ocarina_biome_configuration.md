---
title: Ocarina Biome Configuration
category: biome
---

# Ocarina Biome Configuration

This document details the configuration for the "Ocarina" biome in Noita, focusing on its generation, visual elements, and material composition.

## Topology

The `<Topology>` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base biome definition.
*   **`type`**: "BIOME_WANG_TILE" - Specifies that this biome uses Wang Tiles for generation.
*   **`background_use_neighbor`**: "0" - Disables background image blending with neighboring biomes.
*   **`background_image`**: "data/weather_gfx/background_crypt.png" - Sets the primary background image.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for the background.
*   **`background_edge_priority`**: "12" - Determines the rendering order of background edges.
*   **`wang_template_file`**: "" - No specific Wang Tile template file is used, implying generation is handled by other means or defaults.
*   **`lua_script`**: "data/scripts/biomes/ocarina.lua" - The primary script governing the biome's behavior and generation logic.
*   **`wang_map_width`, `wang_map_height`**: "256" - Defines the dimensions of the generated biome map.
*   **`audio_music_2`**: "wandcave" - Specifies the music track to play in this biome.
*   **`audio_ambience`**: "cave" - Sets the ambient soundscape for the biome.

### BitmapCaves Configuration:

This nested element controls the generation of cave structures within the biome.

*   **`size_x`, `size_y`**: "256" - Dimensions for cave generation.
*   **`spawn_percent`**: "0" - Caves do not spawn based on a percentage.
*   **`blob_caves_count_min`, `blob_caves_count_max`**: "0", "1" - Controls the number of large blob-like cave formations.
*   **`blob_caves_radius_min`, `blob_caves_radius_max`**: "1", "1" - Sets the radius for blob caves.
*   **`blob_caves_strength_min`, `blob_caves_strength_max`**: "1.2", "2" - Defines the intensity of blob caves.
*   **`cave_childs_min`, `cave_childs_max`**: "0", "1" - Controls the number of smaller caves branching off main ones.
*   **`cave_count_min`, `cave_count_max`**: "1", "2" - Sets the number of primary cave systems.
*   **`cave_strength_min`, `cave_strength_max`**: "0.2", "1.8" - Defines the intensity of general cave structures.
*   **`mountain_count_min`, `mountain_count_max`**: "0", "0" - No mountains are generated.
*   **`surface_caves_count_min`, `surface_caves_count_max`**: "0", "0" - No surface caves are generated.

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome.

### Material Components:

Each `<MaterialComponent>` defines a specific material's properties and how it's placed.

| Attribute                 | Value