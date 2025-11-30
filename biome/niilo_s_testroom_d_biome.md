---
title: Niilo's Testroom D Biome
category: biome
---

# Niilo's Testroom D Biome

This document details the configuration for the "niilo_testroom_d" biome in Noita, focusing on its environmental properties and material distribution.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

| Attribute           | Value                                   | Description                                                                 |
| :------------------ | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `name`              | `_EMPTY_`                               | Internal name for this biome configuration.                                 |
| `type`              | `BIOME_WANG_TILE`                       | Specifies the biome generation method (Wang tiles).                         |
| `background_image`  | `data/weather_gfx/background_cave_02.png` | The background image used for this biome.                                   |
| `background_use_neighbor` | `0`                                     | Whether to use background images from neighboring biomes.                   |
| `lua_script`        | `data/scripts/biomes/niilo_testroom_d.lua` | The Lua script that controls biome-specific behaviors and generation.       |
| `wang_map_width`    | `256`                                   | The width of the Wang tile map used for generation.                         |
| `wang_map_height`   | `256`                                   | The height of the Wang tile map used for generation.                        |
| `coarse_map_force_terrain` | `1`                                     | Forces terrain generation on the coarse map.                                |
| `audio_ambience`    | `cave`                                  | The ambient soundscape associated with this biome.                          |
| `noise_biome_edges` | `0`                                     | Disables noise generation at biome edges.                                   |
| `skip_edge_textures`| `1`                                     | Skips texture generation at biome edges.                                    |

## Materials

The `Materials` element defines the distribution and properties of various materials within the biome.

### Material Components

These components specify how different materials are placed and their characteristics.

| Attribute           | Value                                   | Description