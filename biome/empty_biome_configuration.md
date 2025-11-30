---
title: Empty Biome Configuration
category: biome
---

# Empty Biome Configuration

This document details the configuration for the `_EMPTY_` biome in Noita, focusing on its generation parameters and the types of vegetation it can contain.

## Topology

The `Topology` element defines the procedural generation parameters for the biome's terrain and background.

### Key Attributes:

*   **`name`**: `_EMPTY_` - The internal identifier for this biome.
*   **`background_image`**: `data/weather_gfx/background_snowcave.png` - Specifies the background image used for this biome.
*   **`lua_script`**: `data/scripts/biomes/hills.lua` - Links to a Lua script that influences biome generation or behavior.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for terrain generation.
*   **`mGradientAddNoise`**: `1` - Controls the addition of noise to the gradient.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `234.057` - The noise value at the high end of the gradient.
*   **`mGradientLowNoise`**: `-292.571` - The noise value at the low end of the gradient.
*   **`mGradientNoiseScale`**: `0.00128571` - The scaling factor for gradient noise.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.
*   **`mInsidePerlinScaleMax`**: `2` - Maximum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleMin`**: `0.057143` - Minimum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleX`**: `0.9999` - X-axis scaling for Perlin noise.
*   **`mInsidePerlinScaleY`**: `0.9999` - Y-axis scaling for Perlin noise.
*   **`mMultiplierGradient`**: `0.871429` - A multiplier applied to the gradient.

## Materials

The `Materials` element defines the various components and vegetation that can spawn within this biome.

### Vegetation Components:

The `VegetationComponent` elements describe different types of flora and visual elements.

| Attribute                 | Description