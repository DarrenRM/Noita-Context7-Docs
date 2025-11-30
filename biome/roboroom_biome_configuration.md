---
title: Roboroom Biome Configuration
category: biome
---

# Roboroom Biome Configuration

This document details the configuration for the "Roboroom" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

### Key Attributes

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `name`                    | Internal identifier for the biome, "$biome_robobase".                                                      |
| `type`                    | Specifies the biome generation type, "BIOME_WANG_TILE".                                                    |
| `background_image`        | Path to the main background image for the biome.                                                           |
| `background_edge_left`    | Path to the background image for the left edge.                                                            |
| `background_edge_right`   | Path to the background image for the right edge.                                                           |
| `background_edge_top`     | Path to the background image for the top edge.                                                             |
| `background_edge_bottom`  | Path to the background image for the bottom edge.                                                          |
| `background_edge_priority`| Determines the rendering order of background edges.                                                        |
| `lua_script`              | Path to the Lua script that governs biome-specific behaviors and generation.                               |
| `wang_map_width`          | Width of the Wang tile map used for biome generation.                                                      |
| `wang_map_height`         | Height of the Wang tile map used for biome generation.                                                     |
| `audio_music_2`           | Specifies the music track to play in this biome ("vault").                                                 |
| `audio_ambience`          | Specifies the ambient soundscape for this biome ("vault").                                                 |

### BitmapCaves

This section controls the generation of cave-like structures within the biome.

| Attribute                 | Description                                                                                                |
| :------------------------ | :--------------------------------------------------------------------------------------------------------- |
| `size_x`                  | Width of the cave generation area.                                                                         |
| `size_y`                  | Height of the cave generation area.                                                                        |
| `spawn_percent`           | Percentage chance for caves to spawn. Set to "0" for this biome, indicating no random cave generation.     |
| `blob_caves_count_min`    | Minimum number of blob caves.                                                                              |
| `blob_caves_count_max`    | Maximum number of blob caves.                                                                              |
| `blob_caves_radius_min`   | Minimum radius of blob caves.                                                                              |
| `blob_caves_radius_max`   | Maximum radius of blob caves.                                                                              |
| `cave_count_min`          | Minimum number of standard caves.                                                                          |
| `cave_count_max`          | Maximum number of standard caves.                                                                          |
| `cave_strength_min`       | Minimum strength (density/impact) of caves.                                                                |
| `cave_strength_max`       | Maximum strength (density/impact) of caves.                                                                |
| `mountain_count_min`      | Minimum number of mountains. Set to "0" for this biome.                                                    |
| `mountain_count_max`      | Maximum number of mountains. Set to "0" for this biome.                                                    |

## Materials

The `Materials` element defines the various materials that constitute the biome and their properties.

### Key Material Components

Each `MaterialComponent` defines a specific material's presence, distribution, and characteristics.

| Material Name         | Rarity | Y-Limit (Min/Max) | Material Max/Min | Notes