---
title: Boss Arena Biome Configuration
category: biome
---

# Boss Arena Biome Configuration

This document details the configuration for the Boss Arena biome in Noita, focusing on its core properties and how it's defined within the game's data files.

## Biome Topology

The `<Topology>` element defines the fundamental characteristics of the biome.

### Key Attributes:

*   **`name`**: `$biome_boss_arena` - The internal identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for the biome.
*   **`background_use_neighbor`**: `0` - Indicates whether the background should adapt based on adjacent biomes. `0` means it's fixed.
*   **`lua_script`**: `data/scripts/biomes/boss_arena.lua` - The primary script that governs the behavior and generation of this biome.
*   **`wang_map_width` / `wang_map_height`**: `256` / `256` - Dimensions of the Wang map used for terrain generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map, ensuring a defined structure.
*   **`audio_ambience`**: `temple`, `snowcastle` - Defines the ambient soundscapes for the biome.
*   **`audio_music_no_forced_quietness`**: `1` - Prevents the music from being forced into a quiet state.

## Materials

The `<Materials>` element defines the material properties and their distribution within the biome.

### Key Attributes:

*   **`name`**: `temple` - A name associated with the material set, likely referencing a broader category.

**Note:** The provided XML snippet for `<Materials>` is commented out. Typically, this section would contain `<MaterialComponent>` elements defining specific materials, their rarity, and how they are placed (e.g., using polygons for specific shapes). The commented-out examples show how `rock_hard_border` might be defined with polygonal shapes.