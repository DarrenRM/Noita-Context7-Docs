---
title: Temple Altar Biome
category: biome
---

# Temple Altar Biome

This document describes the configuration for the Temple Altar biome in Noita, primarily focusing on its topological and scripting aspects.

## Topology

The `Topology` element defines the core characteristics of the biome.

### Key Attributes:

*   **`name`**: `$biome_holymountain` - A reference name for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for its generation.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image for this biome.
*   **`lua_script`**: `data/scripts/biomes/temple_altar.lua` - The primary script that governs the behavior and generation of this biome.
*   **`wang_map_width`**: `256` - The width of the Wang map used for generation.
*   **`wang_map_height`**: `256` - The height of the Wang map used for generation.
*   **`audio_ambience`**: `temple` - The ambient soundscape associated with this biome.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`pixel_scene`**: `1` - Indicates that this biome uses pixel-based scene generation.

## Materials

The `Materials` element is present but empty in this configuration, suggesting that material definitions for this biome are handled elsewhere or are not explicitly defined within this file.

### Key Attributes:

*   **`name`**: `temple` - A name for the material group.