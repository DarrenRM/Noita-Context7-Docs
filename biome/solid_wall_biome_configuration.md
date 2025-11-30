---
title: Solid Wall Biome Configuration
category: biome
---

# Solid Wall Biome Configuration

This document details the configuration for the "solid_wall" biome in Noita, focusing on its generation parameters and material distribution.

## Topology Settings

The `<Topology>` element defines the fundamental generation characteristics of the biome.

### Key Attributes:

*   `name`: "_EMPTY_" - Indicates this is a base configuration, likely to be overridden or used as a template.
*   `background_image`: "data/weather_gfx/background_cave_02.png" - Specifies the background visual for this biome.
*   `lua_script`: "data/scripts/biomes/hills.lua" - Links to a Lua script that influences biome generation.
*   `mBiomeMaterialsFile`: "data/materials/biome_forest.xml" - References a file defining biome-specific materials.
*   `mExtraPerlinScaleX`, `mExtraPerlinScaleY`: Controls the scaling of extra Perlin noise for terrain generation.
*   `mGradientAddNoise`, `mGradientEndY`, `mGradientHighNoise`, `mGradientLowNoise`, `mGradientMaxY`, `mGradientMinY`, `mGradientNoiseScale`, `mGradientSinMultipleMax`, `mGradientSinMultipleMin`, `mGradientStartY`, `mGradientType`: A suite of parameters that define the gradient-based generation of the biome's shape and features. These control noise, start/end points, and the overall curve.
*   `mInsidePerlinScaleMax`, `mInsidePerlinScaleMin`, `mInsidePerlinScaleX`, `mInsidePerlinScaleY`, `mInsidePerlinScaled`, `mInsidePerlinSquared`: Parameters related to Perlin noise applied *within* the biome's generated shape, affecting its internal texture and detail.
*   `mMultiplierExtraPerlin`, `mMultiplierGradient`, `mMultiplierPerlin`: Multipliers that adjust the influence of different noise and gradient generation methods.
*   `mPerlinScale_x`, `mPerlinScale_y`: Basic scaling for Perlin noise.
*   `mWaterLevel`: Sets the water level for the biome.
*   `has_rain`: "0" - Indicates that rain does not occur in this biome.

## Material Distribution

The `<Materials>` element defines the types and distribution of materials within the "solid_wall" biome.

### Key Attributes:

*   `name`: "solid_wall" - The identifier for this material configuration.

### Material Components:

The `<MaterialComponent>` elements specify individual materials and their properties.

| Attribute                 | Description