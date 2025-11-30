---
title: Mountain Right Entrance Biome
category: biome
---

# Mountain Right Entrance Biome

This document describes the configuration for the "Mountain Right Entrance" biome in Noita, focusing on its terrain generation, material distribution, and visual elements.

## Topology

The `Topology` element defines the procedural generation parameters for the biome's terrain.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/mountain/mountain_right_entrance.lua` - Links to a Lua script that can further customize biome behavior.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise function used for terrain generation.
*   **`mGradientAddNoise`**: `1` - Controls the addition of noise to the gradient.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `234.057` - The noise value at the higher end of the gradient.
*   **`mGradientLowNoise`**: `-292.571` - The noise value at the lower end of the gradient.
*   **`mGradientNoiseScale`**: `0.00128571` - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.
*   **`mInsidePerlinScaleMax`**: `2` - Maximum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleMin`**: `0.057143` - Minimum scale for Perlin noise within the biome.
*   **`mMultiplierGradient`**: `0.871429` - A multiplier applied to the gradient.
*   **`coarse_map_force_terrain`**: `1` - Forces terrain generation on the coarse map.
*   **`audio_ambience`**: `cave` - The ambient soundscape for this biome.

## Materials

The `Materials` element defines the distribution and properties of various materials and visual elements within the biome.

### Material Components:

This section details how different materials are placed and their rarity.

| Attribute                 | Value