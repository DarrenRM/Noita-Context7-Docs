---
title: Tower Biome - Solid Wall Variant
category: biome
---

# Tower Biome - Solid Wall Variant

This document describes the configuration for a specific variant of the Tower biome in Noita, focusing on its solid wall generation and material composition.

## Biome Topology

The `<Topology>` element defines the fundamental characteristics of the biome's generation and appearance.

### Key Attributes:

*   **`name`**: `$biome_tower` - Identifies this as a Tower biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates that this biome uses Wang Tiles for procedural generation.
*   **`background_image`**: `data/weather_gfx/background_crypt.png` - Specifies the background image for the biome.
*   **`wang_template_file`**: `data/wang_tiles/crypt.png` - Points to the Wang Tile template used for generating the biome's structure.
*   **`lua_script`**: `data/scripts/biomes/tower.lua` - The associated Lua script that governs biome-specific behaviors and generation logic.
*   **`audio_music_2`**: `tower` - The music track associated with this biome.
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.

### Bitmap Caves Generation:

The `<BitmapCaves>` element controls the generation of cave-like structures within the biome.

*   **`size_x`, `size_y`**: `516`, `256` - Dimensions of the bitmap used for cave generation.
*   **`blob_caves_radius_min/max`**: `1`, `1` - Controls the minimum and maximum radius of blob-like cave formations.
*   **`cave_strength_min/max`**: `0.2`, `1.8` - Defines the range for the "strength" of generated caves, influencing their shape and density.
*   **`mountain_count_min/max`**: `0`, `0` - Explicitly disables mountain generation in this biome variant.

## Materials

The `<Materials>` element defines the various materials that can spawn within the biome and their properties.

### Material Components:

Each `<MaterialComponent>` defines a specific material and how it's distributed.

| Attribute             | Description