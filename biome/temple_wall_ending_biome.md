---
title: Temple Wall Ending Biome
category: biome
---

# Temple Wall Ending Biome

This document describes the configuration for the "Temple Wall Ending" biome in Noita, primarily focusing on its topological properties and associated scripts.

## Topology

The `Topology` element defines the fundamental characteristics of the biome.

### Key Attributes:

*   **`name`**: `$biome_holymountain` - A unique identifier for this biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for its map generation.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`background_use_neighbor`**: `0` - Controls whether the background image should adapt to neighboring biomes. `0` means it does not.
*   **`wang_template_file`**: `""` - This attribute is empty, suggesting that the Wang Tile template might be defined elsewhere or implicitly.
*   **`lua_script`**: `data/scripts/biomes/temple_wall_ending.lua` - The primary Lua script that governs the behavior and generation of this biome.
*   **`wang_map_width`**: `256` - The width of the Wang map for this biome.
*   **`wang_map_height`**: `256` - The height of the Wang map for this biome.
*   **`limit_background_image`**: `0` - Controls if the background image is limited in its display area. `0` means no limit.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`pixel_scene`**: `1` - Indicates that this biome uses pixel-based scene generation.
*   **`noise_biome_edges`**: `0` - Disables noise generation at biome edges.
*   **`audio_ambience`**: `temple` - Sets the ambient soundscape for this biome to "temple".

## Materials

The `Materials` element is present but empty in this configuration.

### Key Attributes:

*   **`name`**: `temple` - A name associated with the materials used in this biome.

This configuration primarily points to an external Lua script (`temple_wall_ending.lua`) for the detailed definition and behavior of the Temple Wall Ending biome. The `Topology` attributes provide high-level settings for its visual and structural generation.