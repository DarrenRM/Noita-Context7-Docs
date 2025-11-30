---
title: Mountain Hall Trailer Biome
category: biome
---

# Mountain Hall Trailer Biome

This document details the configuration for the "Mountain Hall Trailer" biome in Noita, primarily focusing on its terrain generation and material distribution.

## Topology

The `Topology` element defines the core generation parameters for this biome.

### Key Attributes

| Attribute             | Value                                       | Description                                                                 |
| :-------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `name`                | `_EMPTY_`                                   | Internal name for this biome configuration.                                 |
| `type`                | `BIOME_WANG_TILE`                           | Specifies that this biome uses Wang tiles for terrain generation.           |
| `background_image`    | `data/weather_gfx/background_cave_02.png`   | The background image used for this biome.                                   |
| `background_use_neighbor` | `0`                                         | Indicates if the background should adapt to neighboring biomes.             |
| `lua_script`          | `data/scripts/biomes/mountain/trailer/mountain_hall.lua` | The Lua script that controls biome-specific behaviors and events.           |
| `wang_map_width`      | `256`                                       | The width of the Wang tile map used for terrain generation.                 |
| `wang_map_height`     | `256`                                       | The height of the Wang tile map used for terrain generation.                |
| `coarse_map_force_terrain` | `1`                                         | Forces terrain generation on the coarse map.                                |
| `audio_ambience`      | `temple`                                    | The ambient soundscape associated with this biome.                          |
| `skip_edge_textures`  | `1`                                         | Prevents textures from appearing on the very edges of the biome.            |

## Materials

The `Materials` element defines the various materials that can spawn within this biome and their distribution properties.

### Material Components

This section lists the different `MaterialComponent` elements, each defining a specific material's properties and how it's placed.

| Attribute              | Value