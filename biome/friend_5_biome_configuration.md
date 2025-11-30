---
title: Friend 5 Biome Configuration
category: biome
---

# Friend 5 Biome Configuration

This document details the configuration for the "Friend 5" biome in Noita, focusing on its topological and material properties.

## Topology

The `Topology` element defines the fundamental structure and visual characteristics of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/friend_5.lua` - Links to the biome's associated Lua script for dynamic behavior.
*   **`mBiomeMaterialsFile`**: `data/materials/biome_forest.xml` - References a file that might influence material distribution or properties within this biome.
*   **`mExtraPerlinScaleX`, `mExtraPerlinScaleY`**: Controls the scaling of additional Perlin noise for terrain generation.
*   **`mGradientAddNoise`, `mGradientHighNoise`, `mGradientLowNoise`, `mGradientNoiseScale`**: Parameters for adding and shaping noise within the biome's gradient, influencing terrain irregularity.
*   **`mGradientMaxY`, `mGradientMinY`, `mGradientStartY`, `mGradientEndY`**: Define the vertical range and falloff of the biome's gradient, affecting its overall shape and depth.
*   **`mGradientType`**: `1` - Specifies the type of gradient used for terrain generation.
*   **`mInsidePerlinScaleX`, `mInsidePerlinScaleY`, `mInsidePerlinScaleMax`, `mInsidePerlinScaleMin`**: Control the scaling and influence of Perlin noise for internal cave structures.
*   **`mMultiplierGradient`, `mMultiplierPerlin`**: Adjust the overall impact of gradient and Perlin noise on the biome's terrain.
*   **`mWaterLevel`**: `1000` - Sets the default water level within the biome.
*   **`has_rain`**: `0` - Indicates that rain effects are disabled for this biome.

## Materials

The `Materials` element defines the types and distribution of materials that form the biome's solid structures.

### Key Elements:

The `Materials` element contains `MaterialComponent` children, each defining a specific material and its properties within the biome.

#### `solid_wall` Material Components:

This section details the components that make up the `solid_wall` material.

*   **`MaterialComponent` (coal)**
    *   **`material_name`**: `coal`
    *   **`is_rare`**: `1` - This material is considered rare.
    *   **`limit_min_y`**: `100` - Appears above Y-coordinate 100.
    *   **`material_max`**: `0.55` - Maximum density/influence.
    *   **`material_min`**: `0.51` - Minimum density/influence.
    *   **`rare_polka_probability`**: `0.160871` - Probability of this rare material appearing in a polka pattern.
    *   **`rare_scale_x`, `rare_scale_y`**: `0.0100004`, `0.00357165` - Scaling for the rare distribution pattern.
    *   **`rare_use_polka`**: `1` - Uses a polka distribution for rare occurrences.

*   **`MaterialComponent` (rock_hard)**
    *   **`material_name`**: `rock_hard`
    *   **`is_rare`**: `0` - This material is common.
    *   **`limit_min_y`**: `100` - Appears above Y-coordinate 100.
    *   **`material_max`**: `0.95` - Maximum density/influence.
    *   **`material_min`**: `-100.0` - Minimum density/influence.
    *   **`rare_polka_radius_high`, `rare_polka_radius_low`**: `0.65`, `0.2` - Defines the radius range for polka distribution if used.
    *   **`rare_scale_x`, `rare_scale_y`**: `0.05`, `0.05` - Scaling for the rare distribution pattern.
    *   **`rare_use_polka`**: `1` - Uses a polka distribution for rare occurrences.

*   **`MaterialComponent` (coal - rare variant)**
    *   **`material_name`**: `coal`
    *   **`is_rare`**: `1` - This material is considered rare.
    *   **`limit_min_y`**: `100` - Appears above Y-coordinate 100.
    *   **`material_max`**: `1.2` - Maximum density/influence.
    *   **`material_min`**: `1.1` - Minimum density/influence.
    *   **`rare_polka_probability`**: `0.157143` - Probability of this rare material appearing in a polka pattern.
    *   **`rare_scale_x`, `rare_scale_y`**: `0.0214286`, `0.0214286` - Scaling for the rare distribution pattern.
    *   **`rare_use_perlin`**: `1` - Uses Perlin noise for distribution.
    *   **`rare_use_polka`**: `1` - Uses a polka distribution for rare occurrences.

*   **`MaterialComponent` (copper)**
    *   **`material_name`**: `copper`
    *   **`is_rare`**: `1` - This material is considered rare.
    *   **`limit_min_y`**: `750` - Appears above Y-coordinate 750.
    *   **`material_max`**: `1.25` - Maximum density/influence.
    *   **`material_min`**: `1.05` - Minimum density/influence.
    *   **`rare_polka_probability`**: `0.357143` - Probability of this rare material appearing in a polka pattern.
    *   **`rare_scale_x`, `rare_scale_y`**: `0.007514286`, `0.007514286` - Scaling for the rare distribution pattern.
    *   **`rare_use_perlin`**: `1` - Uses Perlin noise for distribution.
    *   **`rare_use_polka`**: `1` - Uses a polka distribution for rare occurrences.

*   **`MaterialComponent` (rock_hard_border)**
    *   **`material_name`**: `rock_hard_border`
    *   **`is_rare`**: `0` - This material is common.
    *   **`limit_min_y`**: `100` - Appears above Y-coordinate 100.
    *   **`material_max`**: `3.5` - Maximum density/influence.
    *   **`material_min`**: `-0.25` - Minimum density/influence.
    *   **`rare_polka_radius_high`, `rare_polka_radius_low`**: `0.65`, `0.2` - Defines the radius range for polka distribution if used.
    *   **`rare_scale_x`, `rare_scale_y`**: `0.05`, `0.05` - Scaling for the rare distribution pattern.
    *   **`rare_use_polka`**: `1` - Uses a polka distribution for rare occurrences.