---
title: Orbroom 11 Biome Configuration
category: biome
---

# Orbroom 11 Biome Configuration

This document details the configuration for `orbroom_11.xml`, a biome definition for Noita. It focuses on the generation parameters, visual elements, and material distribution within this specific orbroom type.

## Topology

The `<Topology>` element defines the fundamental structure and visual properties of the biome.

### Key Attributes

| Attribute             | Description                                                                 | Value                                                              |
| :-------------------- | :-------------------------------------------------------------------------- | :----------------------------------------------------------------- |
| `name`                | Internal name for the biome.                                                | `$biome_orbroom`                                                   |
| `type`                | Type of biome generation. `BIOME_WANG_TILE` indicates Wang tiling.          | `BIOME_WANG_TILE`                                                  |
| `background_image`    | Path to the main background image.                                          | `data/weather_gfx/background_crypt.png`                            |
| `background_edge_*`   | Paths to edge images for background layering.                               | `data/weather_gfx/edges/background_crypt_*.png`                    |
| `background_edge_priority` | Determines the rendering order of background edges.                         | `11`                                                               |
| `lua_script`          | Path to the Lua script that governs biome-specific logic.                   | `data/scripts/biomes/orbrooms/orbroom_11.lua`                      |
| `wang_map_width`      | Width of the Wang tile map used for generation.                             | `256`                                                              |
| `wang_map_height`     | Height of the Wang tile map used for generation.                            | `256`                                                              |
| `audio_music_2`       | Music track to play in this biome.                                          | `wandcave`                                                         |
| `audio_ambience`      | Ambient soundscape for the biome.                                           | `cave`                                                             |
| `noise_biome_edges`   | Controls whether noise is applied to biome edges.                           | `0` (disabled)                                                     |

### BitmapCaves

This nested element controls the procedural generation of caves within the biome.

| Attribute                 | Description                                       | Value (Min/Max) |
| :------------------------ | :------------------------------------------------ | :-------------- |
| `size_x`, `size_y`        | Dimensions of the bitmap used for cave generation. | `256`           |
| `spawn_percent`           | Percentage of the area to spawn caves.            | `0`             |
| `blob_caves_count_*`      | Number of blob caves to generate.                 | `0` / `1`       |
| `blob_caves_radius_*`     | Radius of blob caves.                             | `1`             |
| `blob_caves_strength_*`   | Strength/impact of blob caves.                    | `1.2` / `2`     |
| `cave_childs_*`           | Number of child caves.                            | `0` / `1`       |
| `cave_count_*`            | Number of main caves.                             | `1` / `2`       |
| `cave_strength_*`         | Strength/impact of main caves.                    | `0.2` / `1.8`   |
| `mountain_count_*`        | Number of mountains to generate.                  | `0`             |
| `surface_caves_count_*`   | Number of surface caves.                          | `0`             |

## Materials

The `<Materials>` element defines the distribution and properties of various materials within the biome.

### MaterialComponent

Each `<MaterialComponent>` defines a specific material and its generation parameters.

| Attribute           | Description