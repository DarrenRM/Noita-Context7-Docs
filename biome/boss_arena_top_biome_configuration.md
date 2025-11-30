---
title: Boss Arena Top Biome Configuration
category: biome
---

# Boss Arena Top Biome Configuration

This document details the configuration for the "Boss Arena Top" biome in Noita, primarily focusing on its `Topology` settings.

## Topology

The `Topology` element defines the core characteristics of the biome.

### Key Attributes:

*   **`name`**: `$biome_boss_arena` - A unique identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`background_use_neighbor`**: `0` - Indicates that the background image is not influenced by neighboring biomes.
*   **`lua_script`**: `data/scripts/biomes/boss_arena_top.lua` - The primary script that governs the behavior and generation of this biome.
*   **`wang_map_width`**: `256` - The width of the Wang map used for terrain generation.
*   **`wang_map_height`**: `256` - The height of the Wang map used for terrain generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`audio_ambience`**: `temple` - Sets the ambient soundscape for the biome.
*   **`audio_music_no_forced_quietness`**: `1` - Prevents forced quietness in the music.
*   **`audio_ambience`**: `snowcastle` - Another ambient soundscape setting, potentially layering or overriding the previous one.

## Materials

The `<Materials />` tag is present but empty, indicating no specific material overrides or additions are defined directly within this biome's XML. Any material properties would likely be handled by the associated Lua script.