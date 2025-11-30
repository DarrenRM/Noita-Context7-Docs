---
title: Orbroom 10 Biome Configuration
category: biome
---

# Orbroom 10 Biome Configuration

This document details the configuration for `orbroom_10.xml`, a biome definition file for Noita. It focuses on the visual and structural aspects of the biome, including its background, cave generation, and material distribution.

## Topology

The `<Topology>` element defines the fundamental properties of the biome's layout and appearance.

### Key Attributes

| Attribute           | Description                                                                                                |
| :------------------ | :--------------------------------------------------------------------------------------------------------- |
| `name`              | Internal name for the biome, "$biome_orbroom".                                                             |
| `type`              | Specifies the biome generation type, "BIOME_WANG_TILE".                                                    |
| `background_use_neighbor` | Controls whether background elements use neighbor data for blending ("0" means no).                      |
| `background_image`  | Path to the main background image for the biome.                                                           |
| `background_edge_*` | Paths to images used for background edges (left, right, top, bottom) for seamless transitions.             |
| `background_edge_priority` | Determines the rendering order of background edges.                                                    |
| `lua_script`        | Path to the Lua script that governs the biome's dynamic behavior and generation logic.                     |
| `wang_map_width`    | Width of the Wang tile map used for biome generation.                                                      |
| `wang_map_height`   | Height of the Wang tile map used for biome generation.                                                     |
| `audio_music_2`     | Specifies the music track to play in this biome ("wandcave").                                              |
| `audio_ambience`    | Specifies the ambient soundscape for this biome ("cave").                                                  |

### BitmapCaves

This nested element configures the procedural generation of caves within the biome.

| Attribute                 | Description