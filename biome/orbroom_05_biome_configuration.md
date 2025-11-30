---
title: Orbroom 05 Biome Configuration
category: biome
---

# Orbroom 05 Biome Configuration

This document details the configuration for `orbroom_05.xml`, a biome definition for Noita. It focuses on the visual and structural aspects of this specific orbroom variant.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's layout and appearance.

### Key Attributes

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `name`                 | Internal identifier for the biome (`$biome_orbroom`).                       |
| `type`                 | Biome generation type (`BIOME_WANG_TILE`).                                  |
| `background_image`     | Path to the main background image for the biome.                            |
| `background_edge_right`| Path to the image for the right edge of the background.                     |
| `background_edge_left` | Path to the image for the left edge of the background.                      |
| `background_edge_top`  | Path to the image for the top edge of the background.                       |
| `background_edge_bottom`| Path to the image for the bottom edge of the background.                    |
| `background_edge_priority`| Determines the layering of background edges.                                |
| `lua_script`           | Path to the Lua script that governs biome-specific behaviors and generation. |
| `wang_map_width`       | Width of the Wang tile map used for generation.                             |
| `wang_map_height`      | Height of the Wang tile map used for generation.                            |
| `audio_music_2`        | Name of the music track to play in this biome.                              |
| `audio_ambience`       | Name of the ambient soundscape for this biome.                              |

### BitmapCaves

This nested element controls the procedural generation of caves within the biome.

#### Key Attributes

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `size_x`                  | Width of the bitmap used for cave generation.                            |
| `size_y`                  | Height of the bitmap used for cave generation.                           |
| `spawn_percent`           | Percentage of the biome area to be filled with caves.                    |
| `blob_caves_count_min`    | Minimum number of large cave blobs.                                      |
| `blob_caves_count_max`    | Maximum number of large cave blobs.                                      |
| `blob_caves_radius_min`   | Minimum radius of large cave blobs.                                      |
| `blob_caves_radius_max`   | Maximum radius of large cave blobs.                                      |
| `blob_caves_strength_min` | Minimum strength/density of large cave blobs.                            |
| `blob_caves_strength_max` | Maximum strength/density of large cave blobs.                            |
| `cave_childs_min`         | Minimum number of smaller caves branching from larger ones.              |
| `cave_childs_max`         | Maximum number of smaller caves branching from larger ones.              |
| `cave_count_min`          | Minimum number of smaller cave structures.                               |
| `cave_count_max`          | Maximum number of smaller cave structures.                               |
| `cave_strength_min`       | Minimum strength/density of smaller cave structures.                     |
| `cave_strength_max`       | Maximum strength/density of smaller cave structures.                     |
| `mountain_count_min`      | Minimum number of mountain-like structures.                              |
| `mountain_count_max`      | Maximum number of mountain-like structures.                              |

## Materials

The `<Materials>` element defines the different types of materials that can appear within the biome and their distribution.

### Key Attributes

| Attribute | Description