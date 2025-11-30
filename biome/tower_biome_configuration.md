---
title: Tower Biome Configuration
category: biome
---

# Tower Biome Configuration

This document details the configuration for the Tower biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the fundamental characteristics of the biome, including its visual appearance, scripting, and dimensions.

### Key Attributes:

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `name`              | Internal identifier for the biome (`$biome_tower`).                         |
| `type`              | Specifies the biome generation method (`BIOME_WANG_TILE`).                  |
| `background_image`  | Path to the main background image for the biome.                            |
| `background_edge_*` | Paths to images used for background edges (left, right, top, bottom).       |
| `background_edge_priority` | Determines the rendering order of background edges.                       |
| `wang_template_file`| Path to the Wang tile template used for generating the biome's structure.   |
| `lua_script`        | Path to the Lua script that governs biome-specific behaviors and generation. |
| `wang_map_width`    | Width of the Wang tile map used for generation.                             |
| `wang_map_height`   | Height of the Wang tile map used for generation.                            |
| `audio_music_2`     | Identifier for the music track associated with this biome.                  |
| `audio_ambience`    | Identifier for the ambient soundscape of this biome.                        |

## Materials

The `Materials` element defines the various materials that can spawn within the biome and their properties.

### Material Components:

Each `MaterialComponent` defines a specific material's spawn conditions and characteristics.

| Attribute             | Description