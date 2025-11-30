---
title: Orbroom 03 Biome Configuration
category: biome
---

---

# Orbroom 03 Biome Configuration

This document details the configuration for `orbroom_03.xml`, a biome definition file for Noita. It outlines the visual, auditory, and material properties of this specific orbroom variant.

## Topology

The `<Topology>` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute             | Description                                                                                                |
| :-------------------- | :--------------------------------------------------------------------------------------------------------- |
| `name`                | Internal identifier for the biome (`$biome_orbroom`).                                                      |
| `type`                | Specifies the biome generation method (`BIOME_WANG_TILE`).                                                 |
| `background_image`    | Path to the main background image (`data/weather_gfx/background_crypt.png`).                               |
| `background_edge_*`   | Paths to images for background edges (left, right, top, bottom) to create seamless transitions.            |
| `background_edge_priority` | Determines the rendering order of background edges (11).                                               |
| `lua_script`          | Path to the associated Lua script for biome-specific logic (`data/scripts/biomes/orbrooms/orbroom_03.lua`). |
| `wang_map_width`      | Width of the Wang tile map used for generation (256).                                                      |
| `wang_map_height`     | Height of the Wang tile map used for generation (256).                                                     |
| `audio_music_2`       | Music track to play in this biome (`wandcave`).                                                            |
| `audio_ambience`      | Ambient soundscape for the biome (`cave`).                                                                 |

### BitmapCaves

This nested element controls the procedural generation of cave structures within the biome.

| Attribute                 | Description                                                                                              |
| :------------------------ | :------------------------------------------------------------------------------------------------------- |
| `size_x`, `size_y`        | Dimensions of the cave generation grid (256x256).                                                        |
| `spawn_percent`           | Percentage of the grid to spawn caves (0, meaning caves are primarily defined by other parameters).        |
| `blob_caves_count_min/max`| Minimum and maximum number of blob caves to generate (0-1).                                              |
| `blob_caves_radius_min/max`| Minimum and maximum radius of blob caves (1).                                                            |
| `blob_caves_strength_min/max`| Minimum and maximum strength/density of blob caves (1.2-2).                                              |
| `cave_childs_min/max`     | Minimum and maximum number of child caves (0-1).                                                         |
| `cave_count_min/max`      | Minimum and maximum number of main caves (1-2).                                                          |
| `cave_strength_min/max`   | Minimum and maximum strength/density of main caves (0.2-1.8).                                            |
| `mountain_count_min/max`  | Minimum and maximum number of mountain structures (0-0, none).                                           |
| `surface_caves_count_min/max`| Minimum and maximum number of surface caves (0-0, none).                                               |

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome.

### Key Attributes

| Attribute | Description