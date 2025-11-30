---
title: Blood Lake Biome Configuration
category: biome
---

# Blood Lake Biome Configuration

This document details the configuration for the "Blood Lake" biome in Noita, focusing on its topological generation and material distribution.

## Topology Generation

The `Topology` element defines the procedural generation of the biome's landscape.

### Key Attributes:

*   **`name`**: `$biome_lake` - Internal identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual.
*   **`lua_script`**: `data/scripts/biomes/lake.lua` - Links to the script that governs biome-specific behaviors.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for terrain generation.
*   **`bitmap_noise_file`**: `data/biome_impl/topology_lake.png` - A bitmap used to influence the topology generation.
*   **`audio_ambience`**: `hills` - The ambient soundscape associated with this biome.

### Gradient and Noise Parameters:

These attributes control the shape and variation of the terrain.

*   **`mGradientAddNoise`**: `3` - Adds noise to the gradient.
*   **`mGradientSlopeStartX`**: `-12000` - Starting X-coordinate for slope calculation.
*   **`mGradientSlopeDelta`**: `-0.37` - The rate of change for the slope.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `134.057` - Controls the upper bound of noise influence.
*   **`mGradientLowNoise`**: `-292.571` - Controls the lower bound of noise influence.
*   **`mGradientNoiseScale`**: `0.00128571` - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.

### Perlin Noise Parameters:

These attributes fine-tune the internal perlin noise used for finer terrain details.

*   **`mInsidePerlinClamped`**: `0` - Whether to clamp the perlin noise output.
*   **`mInsidePerlinScaleMax`**: `1.9999` - Maximum scale for internal perlin noise.
*   **`mInsidePerlinScaleMin`**: `0.057143` - Minimum scale for internal perlin noise.
*   **`mInsidePerlinScaleX`**: `0.009999` - X-axis scale for internal perlin noise.
*   **`mInsidePerlinScaleY`**: `0.009999` - Y-axis scale for internal perlin noise.
*   **`mInsidePerlinScaled`**: `1` - Whether to scale the perlin noise.
*   **`mInsidePerlinSquared`**: `0` - Whether to square the perlin noise output.
*   **`mMultiplierPerlin`**: `1` - Multiplier for perlin noise.
*   **`mInsideAddValue`**: `5.0` - A constant value added to the perlin noise.

*   **`mMultiplierGradient`**: `0.871429` - Multiplier for the overall gradient.

## Material Distribution

The `Materials` element defines how different materials are placed within the biome.

### Key Attributes:

*   **`name`**: `lake` - The identifier for this material set.

### Material Components:

Each `MaterialComponent` defines a specific material and its placement rules.

| Attribute             | Description