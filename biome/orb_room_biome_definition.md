---
title: Orb Room Biome Definition
category: biome
---

# Orb Room Biome Definition

This document details the configuration for the "Orb Room" biome in Noita, focusing on its visual and structural properties.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's layout and appearance.

### Key Attributes

| Attribute              | Description                                                                 |
| :--------------------- | :-------------------------------------------------------------------------- |
| `name`                 | Internal identifier for the biome (`$biome_orbroom`).                       |
| `type`                 | Specifies the biome generation method (`BIOME_WANG_TILE`).                  |
| `background_use_neighbor` | Controls if background elements use neighbor data (0 = no).                 |
| `background_image`     | Path to the main background image (`data/weather_gfx/background_crypt.png`). |
| `background_edge_*`    | Paths to images for background edges (left, right, top, bottom).            |
| `background_edge_priority` | Rendering priority for background edges (11).                               |
| `wang_template_file`   | Path to Wang tile template (empty here, suggesting custom generation).      |
| `lua_script`           | Path to the Lua script controlling biome generation (`data/scripts/biomes/orbrooms/orbroom_01.lua`). |
| `wang_map_width`       | Width of the generated biome map (256).                                     |
| `wang_map_height`      | Height of the generated biome map (256).                                    |
| `audio_music_2`        | Music track to play in this biome (`wandcave`).                             |
| `audio_ambience`       | Ambient soundscape for the biome (`cave`).                                  |

### BitmapCaves

This nested element controls the procedural generation of cave structures within the biome.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `size_x`, `size_y`        | Dimensions of the cave generation grid (256x256).                        |
| `spawn_percent`           | Percentage of the grid to spawn caves (0 = none, suggesting script control). |
| `blob_caves_count_min/max` | Minimum/maximum number of blob-like cave formations.                     |
| `blob_caves_radius_min/max`| Minimum/maximum radius of blob caves.                                    |
| `blob_caves_strength_min/max`| Minimum/maximum intensity of blob caves.                                 |
| `cave_childs_min/max`     | Minimum/maximum number of sub-caves.                                     |
| `cave_count_min/max`      | Minimum/maximum number of main caves.                                    |
| `cave_strength_min/max`   | Minimum/maximum intensity of main caves.                                 |
| `mountain_count_min/max`  | Minimum/maximum number of mountain-like structures (0 here).             |
| `surface_caves_count_min/max`| Minimum/maximum number of surface caves (0 here).                        |

## Materials

The `<Materials>` element defines the types of materials that can appear within the biome and their distribution.

### Key Attributes

| Attribute | Description