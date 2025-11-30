---
title: Sandroom Biome Configuration
category: biome
---

# Sandroom Biome Configuration

This document details the configuration for the "Sandroom" biome in Noita, focusing on its topological properties and material distribution.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `name`                | Internal identifier for the topology, set to `_EMPTY_` for this biome.      |
| `type`                | Specifies the type of topology, `BIOME_WANG_TILE` indicates Wang tiling.    |
| `background_image`    | Path to the background image used for this biome.                           |
| `background_use_neighbor` | Controls if the background image should adapt to neighboring biomes (0 = no). |
| `wang_template_file`  | Path to the Wang tile template file (empty for this biome).                 |
| `lua_script`          | Path to the Lua script that governs biome-specific logic.                   |
| `wang_map_width`      | Width of the Wang tile map.                                                 |
| `wang_map_height`     | Height of the Wang tile map.                                                |
| `coarse_map_force_terrain` | Forces terrain generation on the coarse map (1 = enabled).                |

## Materials

The `Materials` element defines the distribution and properties of various materials within the Sandroom biome.

### Material Components

Each `MaterialComponent` defines a specific material's presence, rarity, and distribution parameters.

| Attribute                 | Description