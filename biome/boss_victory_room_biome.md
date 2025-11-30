---
title: Boss Victory Room Biome
category: biome
---

# Boss Victory Room Biome

This document details the configuration for the Boss Victory Room biome in Noita, focusing on its generation parameters and material composition.

## Topology

The `Topology` element defines the fundamental properties of the biome's generation.

### Key Attributes:

*   **`name`**: `$biome_boss_victoryroom` - A unique identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`background_use_neighbor`**: `0` - Controls whether the background image should adapt to neighboring biomes. `0` means it does not.
*   **`lua_script`**: `data/scripts/biomes/boss_victoryroom.lua` - The Lua script that governs the biome's behavior and generation logic.
*   **`wang_map_width` / `wang_map_height`**: `256` - The dimensions of the Wang map used for generating the biome's layout.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation in the coarse map, ensuring a solid structure.
*   **`audio_ambience`**: `cave` - Sets the ambient soundscape for this biome.

## Materials

The `Materials` element defines the various materials and their distribution within the biome.

### Key Attributes:

*   **`name`**: `the end` - A descriptive name for this material set.

### Material Components:

This section lists the different materials that can appear in the biome and their generation parameters.

| Attribute                 | Description