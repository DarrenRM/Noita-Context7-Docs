---
title: Wizard Cave Biome Configuration
category: biome
---

# Wizard Cave Biome Configuration

This document details the configuration for the Wizard Cave biome in Noita, focusing on its generation parameters, visual elements, and material distribution.

## Biome Topology (`<Topology>`)

This section defines the fundamental generation and visual properties of the Wizard Cave biome.

### Key Attributes:

*   **`name`**: `$biome_wizardcave` - Internal identifier for the biome.
*   **`type`**: `BIOME_WANG_TILE` - Indicates the biome uses Wang Tiles for generation.
*   **`background_image`**: `data/weather_gfx/background_wizardcave.png` - The main background image for the biome.
*   **`wang_template_file`**: `data/wang_tiles/wizardcave.png` - The image file defining the Wang Tile patterns for this biome.
*   **`lua_script`**: `data/scripts/biomes/wizardcave.lua` - The script controlling biome-specific logic and generation.
*   **`audio_music_2`**: `wandcave` - The music track associated with this biome.
*   **`audio_ambience`**: `temple` - The ambient soundscape for this biome.

### Bitmap Caves (`<BitmapCaves>`)

Defines parameters for generating cave structures within the biome.

*   **`size_x`, `size_y`**: Dimensions of the bitmap used for cave generation.
*   **`cave_childs_min`, `cave_childs_max`**: Controls the number of smaller cave systems branching off main ones.
*   **`cave_count_min`, `cave_count_max`**: Defines the number of primary cave systems to generate.
*   **`cave_strength_min`, `cave_strength_max`**: Determines the density and thickness of cave walls.
*   **`spawn_percent`**: Set to `0`, indicating no special spawn percentage for caves themselves.

## Materials (`<Materials>`)

This section defines the various materials present in the Wizard Cave biome and their distribution.

### Material Components (`<MaterialComponent>`)

Each `MaterialComponent` defines a specific material, its rarity, and how it's distributed.

| Attribute                 | Description