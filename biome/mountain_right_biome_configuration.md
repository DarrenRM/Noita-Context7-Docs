---
title: Mountain Right Biome Configuration
category: biome
---

# Mountain Right Biome Configuration

This document details the configuration for the "mountain_right" biome in Noita, focusing on its terrain generation, material distribution, and visual elements.

## Topology

The `Topology` element defines the fundamental shape and characteristics of the biome's terrain.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base configuration, likely to be combined or modified.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background visual for this biome.
*   **`lua_script`**: "data/scripts/biomes/mountain/mountain_right.lua" - Links to a Lua script that likely controls dynamic aspects or further generation logic for this biome.
*   **`noise_type`**: "SIN_CAPPED_SIMPLEX" - Defines the type of noise algorithm used for terrain generation, influencing its organic appearance.
*   **`mGradientAddNoise`**: "1" - Controls the addition of noise to the gradient, affecting terrain smoothness.
*   **`mGradientEndY`**, **`mGradientStartY`**: Define the vertical range for gradient-based terrain shaping.
*   **`mGradientHighNoise`**, **`mGradientLowNoise`**: Set the bounds for noise values applied to the gradient.
*   **`mGradientNoiseScale`**: Controls the scale of the noise applied to the gradient.
*   **`mInsidePerlinScaleMax`**, **`mInsidePerlinScaleMin`**: Define the range for Perlin noise scaling within the biome.
*   **`mMultiplierGradient`**: A multiplier applied to the gradient, affecting terrain height.
*   **`coarse_map_force_terrain`**: "1" - Suggests that this biome strongly influences the coarse map terrain generation.
*   **`audio_ambience`**: "cave" - Sets the default ambient soundscape for this biome.
*   **`skip_edge_textures`**: "1" - Indicates that edge textures should be skipped, likely for smoother transitions.

## Materials

The `Materials` element defines the various materials that can spawn within this biome and their distribution properties.

### Key Material Components:

Each `MaterialComponent` defines a specific material and its spawning parameters.

| Attribute                 | Description