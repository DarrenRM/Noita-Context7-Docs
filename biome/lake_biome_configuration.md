---
title: Lake Biome Configuration
category: biome
---

# Lake Biome Configuration

This document details the configuration for the "Lake" biome in Noita, focusing on its topological generation and material distribution.

## Topology Generation

The `Topology` element defines the procedural generation parameters for the biome's shape and structure.

### Key Attributes:

*   **`name`**: `$biome_lake` - Internal identifier for the biome.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual asset.
*   **`lua_script`**: `data/scripts/biomes/lake.lua` - Links to the script that governs biome-specific behaviors.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for terrain generation.
*   **`mGradientAddNoise`**: `3` - Adds a base level of noise to the gradient.
*   **`mGradientSlopeStartX`**: `-12000` - The starting X-coordinate for the gradient slope.
*   **`mGradientSlopeDelta`**: `-0.37` - The rate of change for the gradient slope.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `134.057` - Controls the upper bound of noise influence on the gradient.
*   **`mGradientLowNoise`**: `-292.571` - Controls the lower bound of noise influence on the gradient.
*   **`mGradientNoiseScale`**: `0.00128571` - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.
*   **`bitmap_noise_file`**: `data/biome_impl/topology_lake.png` - A bitmap texture used to further influence topology generation.
*   **`audio_ambience`**: `hills` - The ambient soundscape for this biome.
*   **`audio_music_enter`**: `music/oneshot/02` - The music track that plays upon entering the biome.

## Material Distribution

The `Materials` element defines how different materials are placed within the biome based on various parameters.

### Key Material Components:

The `MaterialComponent` elements specify the material name, its distribution range (min/max Y-coordinates), and how it's generated. The `rare_` attributes are used for special distribution patterns, often referred to as "polka dots" or clustered appearances.

| Attribute                 | Description