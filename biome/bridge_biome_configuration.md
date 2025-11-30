---
title: Bridge Biome Configuration
category: biome
---

# Bridge Biome Configuration

This document details the configuration for the "bridge" biome in Noita, focusing on its generation parameters and the materials and vegetation it contains.

## Topology

The `<Topology>` element defines the procedural generation parameters for the biome's shape and appearance.

### Key Attributes:

*   `name`: "_EMPTY_" - Indicates this is a base or empty topology definition.
*   `background_image`: "data/weather_gfx/background_snowcave.png" - Specifies the background visual for this biome.
*   `lua_script`: "data/scripts/biomes/bridge.lua" - Links to the script that governs biome-specific behaviors.
*   `noise_type`: "SIN_CAPPED_SIMPLEX" - The type of noise algorithm used for terrain generation.
*   `mGradientAddNoise`: "1" - Controls the addition of noise to the gradient.
*   `mGradientEndY`: "1024" - The Y-coordinate where the gradient ends.
*   `mGradientHighNoise`: "234.057" - The noise value at the high end of the gradient.
*   `mGradientLowNoise`: "-292.571" - The noise value at the low end of the gradient.
*   `mGradientNoiseScale`: "0.00128571" - Scales the noise applied to the gradient.
*   `mGradientStartY`: "-1024" - The Y-coordinate where the gradient starts.
*   `mInsidePerlinScaleMax`: "2" - Maximum scale for Perlin noise within the biome.
*   `mInsidePerlinScaleMin`: "0.057143" - Minimum scale for Perlin noise within the biome.
*   `mInsidePerlinScaled`: "1" - Whether Perlin noise scaling is applied.
*   `mMultiplierGradient`: "0.871429" - A multiplier applied to the gradient.

## Materials and Vegetation

The `<Materials>` element defines the various components that make up the biome, including ground materials and vegetation.

### Key Vegetation Components:

The `VegetationComponent` elements define the types of flora that can spawn within this biome.

| Attribute             | Description