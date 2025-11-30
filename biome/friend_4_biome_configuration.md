---
title: Friend 4 Biome Configuration
category: biome
---

# Friend 4 Biome Configuration

This document details the configuration for the "Friend 4" biome in Noita, focusing on its topological generation and material distribution.

## Topology

The `Topology` element defines the fundamental structure and visual characteristics of the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base biome definition.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background image used for this biome.
*   **`lua_script`**: "data/scripts/biomes/friend_4.lua" - Links to a Lua script that can further customize biome behavior.
*   **`mBiomeMaterialsFile`**: "data/materials/biome_forest.xml" - References a file defining the default materials for this biome.
*   **`mExtraPerlinScaleX`, `mExtraPerlinScaleY`**: Controls the scaling of extra Perlin noise for terrain generation.
*   **`mGradientAddNoise`, `mGradientEndY`, `mGradientHighNoise`, `mGradientLowNoise`, `mGradientMaxY`, `mGradientMinY`, `mGradientNoiseScale`, `mGradientSinMultipleMax`, `mGradientSinMultipleMin`, `mGradientStartY`, `mGradientType`**: A comprehensive set of parameters controlling gradient-based terrain shaping, including noise, start/end points, and sinusoidal variations.
*   **`mInsidePerlinScaleMax`, `mInsidePerlinScaleMin`, `mInsidePerlinScaleX`, `mInsidePerlinScaleY`, `mInsidePerlinScaled`, `mInsidePerlinSquared`**: Parameters for controlling Perlin noise applied to the interior of the biome.
*   **`mMultiplierExtraPerlin`, `mMultiplierGradient`, `mMultiplierPerlin`**: Multipliers that adjust the influence of different noise and gradient generation methods.
*   **`mPerlinScale_x`, `mPerlinScale_y`**: Basic Perlin noise scaling parameters.
*   **`mWaterLevel`**: "1000" - Sets the water level for the biome.
*   **`has_rain`**: "0" - Indicates that rain is disabled for this biome.

## Materials

The `Materials` element defines the types and distribution of materials within the biome. The `name="solid_wall"` attribute indicates these materials form the primary solid structures.

### Material Components:

Each `MaterialComponent` defines a specific material and its properties within the biome.

#### `coal` (Rare)

*   **`is_rare`**: "1" - This material is not guaranteed to appear.
*   **`limit_max_y`**: "2048" - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: "100" - Minimum Y-coordinate for this material.
*   **`material_name`**: "coal" - The name of the material.
*   **`material_max`**: "0.55" - Maximum influence of this material.
*   **`material_min`**: "0.51" - Minimum influence of this material.
*   **`rare_polka_probability`**: "0.160871" - Probability of this material appearing in a "polka" pattern.
*   **`rare_scale_x`, `rare_scale_y`**: "0.0100004", "0.00357165" - Scaling for Perlin noise used in distribution.
*   **`rare_use_polka`**: "1" - Enables a polka-like distribution pattern.

#### `rock_hard` (Common)

*   **`is_rare`**: "0" - This material is common.
*   **`limit_max_y`**: "2048" - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: "100" - Minimum Y-coordinate for this material.
*   **`material_name`**: "rock_hard" - The name of the material.
*   **`material_max`**: "0.95" - Maximum influence of this material.
*   **`material_min`**: "-100.0" - Minimum influence of this material.
*   **`rare_polka_probability`**: "0.2" - Probability of this material appearing in a "polka" pattern.
*   **`rare_scale_x`, `rare_scale_y`**: "0.05", "0.05" - Scaling for Perlin noise used in distribution.
*   **`rare_use_polka`**: "1" - Enables a polka-like distribution pattern.

#### `coal` (Rare, different distribution)

*   **`is_rare`**: "1" - This material is rare.
*   **`limit_max_y`**: "2048" - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: "100" - Minimum Y-coordinate for this material.
*   **`material_name`**: "coal" - The name of the material.
*   **`material_max`**: "1.2" - Maximum influence of this material.
*   **`material_min`**: "1.1" - Minimum influence of this material.
*   **`rare_polka_probability`**: "0.157143" - Probability of this material appearing in a "polka" pattern.
*   **`rare_scale_x`, `rare_scale_y`**: "0.0214286", "0.0214286" - Scaling for Perlin noise used in distribution.
*   **`rare_use_perlin`**: "1" - Enables Perlin noise for distribution.
*   **`rare_use_polka`**: "1" - Enables a polka-like distribution pattern.

#### `copper` (Rare)

*   **`is_rare`**: "1" - This material is rare.
*   **`limit_max_y`**: "2048" - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: "750" - Minimum Y-coordinate for this material.
*   **`material_name`**: "copper" - The name of the material.
*   **`material_max`**: "1.25" - Maximum influence of this material.
*   **`material_min`**: "1.05" - Minimum influence of this material.
*   **`rare_polka_probability`**: "0.357143" - Probability of this material appearing in a "polka" pattern.
*   **`rare_scale_x`, `rare_scale_y`**: "0.007514286", "0.007514286" - Scaling for Perlin noise used in distribution.
*   **`rare_use_perlin`**: "1" - Enables Perlin noise for distribution.
*   **`rare_use_polka`**: "1" - Enables a polka-like distribution pattern.

#### `rock_hard_border` (Common)

*   **`is_rare`**: "0" - This material is common.
*   **`limit_max_y`**: "2048" - Maximum Y-coordinate for this material.
*   **`limit_min_y`**: "100" - Minimum Y-coordinate for this material.
*   **`material_name`**: "rock_hard_border" - The name of the material.
*   **`material_max`**: "3.5" - Maximum influence of this material.
*   **`material_min`**: "-0.25" - Minimum influence of this material.
*   **`rare_polka_probability`**: "0.2" - Probability of this material appearing in a "polka" pattern.
*   **`rare_scale_x`, `rare_scale_y`**: "0.05", "0.05" - Scaling for Perlin noise used in distribution.
*   **`rare_use_polka`**: "1" - Enables a polka-like distribution pattern.