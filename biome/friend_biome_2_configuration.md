---
title: Friend Biome 2 Configuration
category: biome
---

# Friend Biome 2 Configuration

This document details the configuration for the "Friend Biome 2" in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental generation characteristics of the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base biome definition.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/friend_2.lua` - Links to the Lua script that further defines biome behavior and generation.
*   **`mBiomeMaterialsFile`**: `data/materials/biome_forest.xml` - References an external file for base material definitions.
*   **`mGradientEndY`**, **`mGradientStartY`**: Define the vertical range for gradient-based generation.
*   **`mGradientType`**: `1` - Suggests a specific gradient generation algorithm.
*   **`mInsidePerlinScaleX`**, **`mInsidePerlinScaleY`**: Control the scaling of Perlin noise for internal structure generation.
*   **`mMultiplierGradient`**, **`mMultiplierPerlin`**: Influence the overall impact of gradient and Perlin noise on the biome's shape.
*   **`mWaterLevel`**: `1000` - Sets the default water level within the biome.

## Materials

The `Materials` element defines how different materials are distributed within the biome. The `name="solid_wall"` indicates these materials form the primary solid structures.

### Material Components:

Each `MaterialComponent` defines a specific material's properties and how it's placed.

| Attribute                 | Description