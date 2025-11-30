---
title: Meat Room Biome Configuration
category: biome
---

# Meat Room Biome Configuration

This document details the configuration for the "Meat Room" biome in Noita, focusing on its visual, structural, and material properties.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

| Attribute Name              | Description                                                                                                | Example Value                     |
| :-------------------------- | :--------------------------------------------------------------------------------------------------------- | :-------------------------------- |
| `name`                      | Internal identifier for the biome.                                                                         | `$biome_meat`                     |
| `type`                      | Specifies the generation method (Wang Tile system).                                                        | `BIOME_WANG_TILE`                 |
| `background_image`          | Path to the main background image.                                                                         | `data/weather_gfx/background_the_end.png` |
| `background_edge_left`      | Path to the left edge background image.                                                                    | `data/weather_gfx/edges/background_the_end_left.png` |
| `background_edge_right`     | Path to the right edge background image.                                                                   | `data/weather_gfx/edges/background_the_end_right.png` |
| `background_edge_top`       | Path to the top edge background image.                                                                     | `data/weather_gfx/edges/background_the_end_top.png` |
| `background_edge_bottom`    | Path to the bottom edge background image.                                                                  | `data/weather_gfx/edges/background_the_end_bottom.png` |
| `background_edge_priority`  | Determines the layering of background elements. Higher values are drawn on top.                            | `9`                               |
| `lua_script`                | Path to the Lua script that controls biome-specific logic and events.                                      | `data/scripts/biomes/meatroom.lua` |
| `wang_map_width`            | Width of the Wang map used for generation.                                                                 | `256`                             |
| `wang_map_height`           | Height of the Wang map used for generation.                                                                | `256`                             |
| `audio_music_2`             | Specifies the music track to play in this biome.                                                           | `rainforest`                      |
| `audio_music_energy_coeff`  | Coefficient affecting music intensity based on game energy.                                                | `2`                               |
| `audio_music_forced_quietness_duration_seconds` | Duration in seconds for forced quietness in music.                                         | `4`                               |
| `audio_ambience`            | Specifies the ambient soundscape for the biome.                                                            | `rainforest`                      |

### BitmapCaves Configuration:

The `<BitmapCaves>` element controls the generation of cave-like structures within the biome.

| Attribute Name            | Description                                                              | Example Value |
| :------------------------ | :----------------------------------------------------------------------- | :------------ |
| `size_x`                  | Width of the bitmap used for cave generation.                            | `256`         |
| `size_y`                  | Height of the bitmap used for cave generation.                           | `256`         |
| `spawn_percent`           | Percentage of the map where caves can spawn.                             | `0`           |
| `blob_caves_count_min`    | Minimum number of blob caves to generate.                                | `0`           |
| `blob_caves_count_max`    | Maximum number of blob caves to generate.                                | `1`           |
| `blob_caves_radius_min`   | Minimum radius of blob caves.                                            | `1`           |
| `blob_caves_radius_max`   | Maximum radius of blob caves.                                            | `1`           |
| `blob_caves_strength_min` | Minimum strength (density/impact) of blob caves.                         | `1.2`         |
| `blob_caves_strength_max` | Maximum strength (density/impact) of blob caves.                         | `2`           |
| `cave_childs_min`         | Minimum number of child caves branching from main caves.                 | `0`           |
| `cave_childs_max`         | Maximum number of child caves branching from main caves.                 | `1`           |
| `cave_count_min`          | Minimum number of main caves to generate.                                | `1`           |
| `cave_count_max`          | Maximum number of main caves to generate.                                | `2`           |
| `cave_strength_min`       | Minimum strength (density/impact) of main caves.                         | `0.2`         |
| `cave_strength_max`       | Maximum strength (density/impact) of main caves.                         | `1.8`         |
| `mountain_count_min`      | Minimum number of mountain structures to generate.                       | `0`           |
| `mountain_count_max`      | Maximum number of mountain structures to generate.                       | `0`           |

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome.

### Key Material Components:

The `<MaterialComponent>` elements specify individual materials and their properties.

| Attribute Name        | Description