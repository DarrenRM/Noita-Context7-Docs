---
title: Niilo's Testroom C Biome Configuration
category: biome
---

# Niilo's Testroom C Biome Configuration

This document details the configuration for the `niilo_testroom_c.xml` biome file, used in Noita modding. It focuses on key attributes for AI-assisted mod development.

## Topology

The `<Topology>` element defines the fundamental properties of the biome.

### Key Attributes:

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `name`              | Internal name for the biome topology.                                       |
| `type`              | Specifies the type of biome, here `BIOME_WANG_TILE` for Wang Tile generation. |
| `background_image`  | Path to the background image used for this biome.                           |
| `background_use_neighbor` | Controls if the background image should blend with neighboring biomes.      |
| `wang_template_file`| Path to the Wang Tile template file used for terrain generation.            |
| `lua_script`        | Path to the Lua script that governs biome-specific logic and events.        |
| `wang_map_width`    | The width of the Wang map used for terrain generation.                    |
| `wang_map_height`   | The height of the Wang map used for terrain generation.                   |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map.                            |
| `audio_ambience`    | The ambient soundscape associated with this biome.                          |

## Materials

The `<Materials>` element defines the different materials that can spawn within this biome and their properties.

### Key Attributes:

| Attribute | Description