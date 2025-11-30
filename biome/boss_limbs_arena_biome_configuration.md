---
title: Boss Limbs Arena Biome Configuration
category: biome
---

# Boss Limbs Arena Biome Configuration

This document details the configuration for the `boss_limbs_arena.xml` biome file, which defines the properties and materials for a specific arena-style biome in Noita.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes

| Attribute             | Description                                                                 | Example Value                      |
| :-------------------- | :-------------------------------------------------------------------------- | :--------------------------------- |
| `name`                | Internal name for this biome configuration.                                 | `_EMPTY_`                          |
| `type`                | Specifies the biome generation type. `BIOME_WANG_TILE` indicates wang tiling. | `BIOME_WANG_TILE`                  |
| `background_image`    | Path to the background image used for this biome.                           | `data/weather_gfx/background_cave_02.png` |
| `background_use_neighbor` | Controls if the background image should blend with neighboring biomes.      | `0`                                |
| `wang_template_file`  | Path to the wang tile template file (if applicable).                        | `""` (empty, not used here)        |
| `lua_script`          | Path to a Lua script that can further customize biome generation.           | `data/scripts/biomes/boss_limbs_arena.lua` |
| `wang_map_width`      | The width of the wang map used for generation.                              | `256`                              |
| `wang_map_height`     | The height of the wang map used for generation.                             | `256`                              |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map.                              | `1`                                |
| `audio_ambience`      | The ambient soundscape to play in this biome.                               | `cave`                             |
| `noise_biome_edges`   | Controls noise generation at biome edges.                                   | `0`                                |
| `skip_edge_textures`  | Skips texture generation at biome edges.                                    | `1`                                |

## Materials

The `<Materials>` element defines the different material components that can appear within this biome and their generation properties.

### Key Attributes

| Attribute | Description