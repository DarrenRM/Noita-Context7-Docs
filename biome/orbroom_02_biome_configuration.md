---
title: Orbroom 02 Biome Configuration
category: biome
---

# Orbroom 02 Biome Configuration

This document details the configuration for `orbroom_02.xml`, a biome definition for Noita. It focuses on the visual and structural aspects of this specific orbroom variant.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's layout and appearance.

### Key Attributes

| Attribute              | Description                                                                                             |
| :--------------------- | :------------------------------------------------------------------------------------------------------ |
| `name`                 | Internal name for the biome, "$biome_orbroom".                                                          |
| `type`                 | Specifies the biome generation type, "BIOME_WANG_TILE".                                                 |
| `background_use_neighbor` | Controls whether the background image uses neighboring biome data, set to "0" (disabled).              |
| `background_image`     | Path to the main background image for this biome.                                                       |
| `background_edge_left` | Path to the left edge graphic for the background.                                                       |
| `background_edge_right`| Path to the right edge graphic for the background.                                                      |
| `background_edge_top`  | Path to the top edge graphic for the background.                                                        |
| `background_edge_bottom`| Path to the bottom edge graphic for the background.                                                     |
| `background_edge_priority`| Determines the rendering priority of background edges, set to "11".                                   |
| `wang_template_file`   | Path to the Wang tile template file (empty in this case).                                               |
| `lua_script`           | Path to the Lua script that governs biome-specific logic and generation.                                |
| `wang_map_width`       | Width of the Wang map used for generation.                                                              |
| `wang_map_height`      | Height of the Wang map used for generation.                                                             |
| `audio_music_2`        | Specifies the music track to play in this biome, "wandcave".                                            |
| `audio_ambience`       | Specifies the ambient soundscape for this biome, "cave".                                                |

### BitmapCaves

This section defines parameters for generating cave-like structures within the biome.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `size_x`                  | Width of the cave generation area.                                                                      |
| `size_y`                  | Height of the cave generation area.                                                                     |
| `spawn_percent`           | Percentage of the area to spawn caves (set to "0", suggesting manual placement or script control).      |
| `blob_caves_count_min`    | Minimum number of blob caves.                                                                           |
| `blob_caves_count_max`    | Maximum number of blob caves.                                                                           |
| `blob_caves_radius_min`   | Minimum radius of blob caves.                                                                           |
| `blob_caves_radius_max`   | Maximum radius of blob caves.                                                                           |
| `blob_caves_strength_min` | Minimum strength of blob caves (influences density/shape).                                              |
| `blob_caves_strength_max` | Maximum strength of blob caves.                                                                         |
| `cave_childs_min`         | Minimum number of child caves branching from main caves.                                                |
| `cave_childs_max`         | Maximum number of child caves.                                                                          |
| `cave_count_min`          | Minimum number of main caves.                                                                           |
| `cave_count_max`          | Maximum number of main caves.                                                                           |
| `cave_strength_min`       | Minimum strength of main caves.                                                                         |
| `cave_strength_max`       | Maximum strength of main caves.                                                                         |
| `mountain_count_min`      | Minimum number of mountain-like structures (set to "0").                                                |
| `mountain_count_max`      | Maximum number of mountain-like structures (set to "0").                                                |
| `surface_caves_count_min` | Minimum number of surface caves (set to "0").                                                           |
| `surface_caves_count_max` | Maximum number of surface caves (set to "0").                                                           |

## Materials

The `<Materials>` element defines the different types of materials that can be found within the biome and their distribution.

### Material Components

Each `<MaterialComponent>` defines a specific material and its properties.

| Attribute             | Description