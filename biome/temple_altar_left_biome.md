---
title: Temple Altar Left Biome
category: biome
---

# Temple Altar Left Biome

This document describes the `temple_altar_left.xml` file, which defines a biome in Noita.

## Topology

The `Topology` element defines the core properties of the biome.

### Key Attributes:

*   **name**: `$biome_holymountain` - Internal identifier for this biome.
*   **type**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for its map generation.
*   **background_image**: `data/weather_gfx/background_cave_02.png` - The background image used for this biome.
*   **lua_script**: `data/scripts/biomes/temple_altar_left.lua` - The Lua script that controls the biome's behavior and generation.
*   **wang_map_width**: `256` - The width of the Wang Tile map for this biome.
*   **wang_map_height**: `256` - The height of the Wang Tile map for this biome.
*   **audio_ambience**: `temple` - The ambient soundscape associated with this biome.
*   **coarse_map_force_terrain**: `1` - Forces terrain generation on the coarse map.
*   **pixel_scene**: `1` - Enables pixel-based scene rendering for this biome.

## Materials

The `Materials` element is used to define the materials present within the biome.

### Key Attributes:

*   **name**: `temple` - The name associated with the materials used in this biome.

This section is currently empty in the provided XML, suggesting that material definitions are likely handled within the associated Lua script or other linked files.