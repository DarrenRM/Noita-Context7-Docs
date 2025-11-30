---
title: Snowcastle Biome Configuration
category: biome
---

# Snowcastle Biome Configuration

This document details the configuration for the Snowcastle biome in Noita, focusing on its visual and material properties.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome, including its visual assets, scripting, and audio.

### Key Attributes:

| Attribute             | Description                                                                 | Example Value                               |
| :-------------------- | :-------------------------------------------------------------------------- | :------------------------------------------ |
| `name`                | Internal identifier for the biome.                                          | `$biome_snowcastle`                         |
| `type`                | Type of biome generation (Wang Tiles).                                      | `BIOME_WANG_TILE`                           |
| `background_image`    | Path to the main background image for the biome.                            | `data/weather_gfx/background_snowcastle.png`|
| `background_edge_*`   | Paths to images for background edges (left, right, top, bottom).            | `data/weather_gfx/edges/background_snowcastle_left.png` |
| `wang_template_file`  | Path to the Wang Tile image used for generating the biome's structure.      | `data/wang_tiles/snowcastle.png`            |
| `lua_script`          | Path to the Lua script that controls biome-specific behaviors and events.   | `data/scripts/biomes/snowcastle.lua`        |
| `audio_music_2`       | Name of the music track to play in this biome.                              | `snowcastle`                                |
| `audio_ambience`      | Name of the ambient soundscape for this biome.                              | `snowcastle`                                |

## Materials

The `<Materials>` element defines the different material components that make up the biome's terrain and their distribution.

### Material Components:

Each `<MaterialComponent>` defines a specific material and its properties within the biome.

| Attribute             | Description