---
title: Snowcave Tunnel Biome Configuration
category: biome
---

# Snowcave Tunnel Biome Configuration

This document details the configuration for the `snowcave_tunnel.xml` biome in Noita, focusing on its visual and material properties.

## Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies the biome uses Wang tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_snowcave.png` - The primary background image for this biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: Paths to specific edge graphics for seamless background transitions.
*   **`background_edge_priority`**: `9` - Controls the layering of background elements.
*   **`lua_script`**: `data/scripts/biomes/snowcave.lua` - The associated Lua script that governs biome-specific behaviors and generation logic.
*   **`wang_map_width`, `wang_map_height`**: `256` - Dimensions of the Wang tile map used for generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`audio_ambience`**: `cave` - Specifies the ambient soundscape for this biome.
*   **`skip_edge_textures`**: `1` - Skips rendering of edge textures for this biome.

## Materials

The `<Materials>` element defines the distribution and properties of various materials within the biome.

### Key Attributes:

*   **`name`**: `lavalake` - This name seems to be a remnant or placeholder, as the components describe snowcave materials.

### Material Components:

Each `<MaterialComponent>` defines a specific material's presence and characteristics within the biome.

| Attribute                 | Description