---
title: Teleroom Biome Configuration
category: biome
---

# Teleroom Biome Configuration

This document details the configuration for the "Teleroom" biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `<Topology>` element defines the fundamental generation characteristics of the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base topology definition.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background visual for this biome.
*   **`lua_script`**: "data/scripts/biomes/teleroom.lua" - Links to the primary script that governs the biome's behavior and generation logic.
*   **`mExtraPerlinScaleX`**, **`mExtraPerlinScaleY`**: Controls the scaling of additional Perlin noise for terrain variation.
*   **`mGradientAddNoise`**, **`mGradientHighNoise`**, **`mGradientLowNoise`**, **`mGradientNoiseScale`**: Parameters for generating a gradient-based terrain shape with added noise.
*   **`mGradientMaxY`**, **`mGradientMinY`**, **`mGradientStartY`**, **`mGradientEndY`**: Define the vertical range and falloff of the gradient.
*   **`mMultiplierGradient`**, **`mMultiplierPerlin`**: Influence the overall impact of gradient and Perlin noise on the terrain shape.
*   **`mWaterLevel`**: "1000" - Sets the default water level within the biome.

## Materials

The `<Materials>` element defines the types and distribution of materials within the biome. The `name="solid_wall"` indicates these materials form the primary solid structures.

### Material Components:

Each `<MaterialComponent>` defines a specific material's properties and how it's distributed.

| Attribute                 | Description