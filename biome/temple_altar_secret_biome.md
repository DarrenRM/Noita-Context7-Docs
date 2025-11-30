---
title: Temple Altar Secret Biome
category: biome
---

# Temple Altar Secret Biome

This document describes the configuration for the "Temple Altar Secret" biome in Noita, primarily focusing on its topological properties and associated scripts.

## Topology

The `<Topology>` element defines the fundamental characteristics of this biome.

### Key Attributes:

*   **`name`**: `$biome_holymountain` - Identifies this biome, likely as a variant or part of the Holy Mountain system.
*   **`type`**: `BIOME_WANG_TILE` - Indicates that this biome uses a Wang Tile system for its generation.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`background_use_neighbor`**: `0` - Suggests that the background image is not influenced by neighboring biomes.
*   **`lua_script`**: `data/scripts/biomes/temple_altar_secret.lua` - The primary script responsible for the biome's logic and behavior.
*   **`wang_map_width`**: `256` - The width of the Wang map used for generation.
*   **`wang_map_height`**: `256` - The height of the Wang map used for generation.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`pixel_scene`**: `1` - Indicates that the biome is rendered as a pixel scene.
*   **`audio_ambience`**: `temple` - Sets the ambient audio theme for this biome.

## Materials

The `<Materials>` element is present but empty in this configuration, suggesting that material definitions for this specific biome might be handled elsewhere or are not explicitly defined within this file.

*   **`name`**: `temple` - A general name for the material set, likely inherited or a placeholder.