---
title: Alchemist Secret Biome Configuration
category: biome
---

# Alchemist Secret Biome Configuration

This document details the configuration for the "Alchemist Secret" biome in Noita, focusing on its generation, visual elements, and material composition.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   `name`: "???" - The internal name for this biome topology.
*   `type`: "BIOME_WANG_TILE" - Indicates this biome uses Wang Tiles for generation.
*   `background_use_neighbor`: "0" - Disables background image blending with neighbors.
*   `background_image`: "data/weather_gfx/background_crypt.png" - The primary background image for this biome.
*   `background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`: Paths to specific edge graphics for the background.
*   `background_edge_priority`: "12" - Determines the rendering order of background edges.
*   `wang_template_file`: "" - Specifies a Wang Tile template file (empty here, suggesting default or script-driven).
*   `lua_script`: "data/scripts/biomes/alchemist_secret.lua" - The associated Lua script that controls biome generation and behavior.
*   `wang_map_width`, `wang_map_height`: "256" - Dimensions of the generated biome map.
*   `audio_music_2`: "wandcave" - The music track to play in this biome.
*   `audio_ambience`: "cave" - The ambient soundscape for this biome.

### BitmapCaves:

This section defines parameters for generating cave structures within the biome.

*   `size_x`, `size_y`: "256" - Dimensions for bitmap cave generation.
*   `spawn_percent`: "0" - No random cave spawning based on percentage.
*   `blob_caves_count_min`, `blob_caves_count_max`: "0" to "1" - Controls the number of blob-like cave formations.
*   `blob_caves_radius_min`, `blob_caves_radius_max`: "1" to "2" - Defines the size range of blob caves.
*   `blob_caves_strength_min`, `blob_caves_strength_max`: "1.2" to "2" - Controls the density/impact of blob caves.
*   `cave_childs_min`, `cave_childs_max`: "0" to "1" - Number of smaller cave systems branching off main ones.
*   `cave_count_min`, `cave_count_max`: "1" to "2" - The number of primary cave systems.
*   `cave_strength_min`, `cave_strength_max`: "0.2" to "1.8" - Controls the density/impact of general caves.
*   `mountain_count_min`, `mountain_count_max`: "0" - No mountain generation.

## Materials

The `Materials` element defines the types and distribution of materials within the biome.

### Material Components:

Each `MaterialComponent` defines a specific material's properties and how it's placed.

| Attribute                 | Description