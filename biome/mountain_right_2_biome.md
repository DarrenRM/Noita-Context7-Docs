---
title: Mountain Right 2 Biome
category: biome
---

# Mountain Right 2 Biome

This document describes the configuration for the "mountain_right_2" biome in Noita, focusing on its terrain generation and material distribution.

## Topology

The `Topology` element defines the procedural generation parameters for the biome's terrain shape and background.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this biome doesn't have a specific predefined terrain shape.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background image used for this biome.
*   **`lua_script`**: "data/scripts/biomes/mountain/mountain_right_2.lua" - Links to a Lua script that can further customize biome generation or behavior.
*   **`noise_type`**: "SIN_CAPPED_SIMPLEX" - The type of noise function used for terrain generation.
*   **`mGradientAddNoise`**: "1" - Controls whether noise is added to the gradient.
*   **`mGradientEndY`**: "1024" - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: "234.057" - The upper bound for gradient noise.
*   **`mGradientLowNoise`**: "-292.571" - The lower bound for gradient noise.
*   **`mGradientNoiseScale`**: "0.00128571" - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: "-1024" - The Y-coordinate where the gradient starts.
*   **`mInsidePerlinScaleMax`**: "2" - Maximum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleMin`**: "0.057143" - Minimum scale for Perlin noise within the biome.
*   **`mMultiplierGradient`**: "0.871429" - A multiplier applied to the gradient.
*   **`coarse_map_force_terrain`**: "1" - Forces terrain generation on the coarse map.
*   **`audio_ambience`**: "cave" - Sets the ambient soundscape for this biome.

## Materials

The `Materials` element defines the various materials that can spawn within this biome and their distribution properties.

### Material Components:

This section lists different material types and their specific generation parameters.

| Attribute                 | Value