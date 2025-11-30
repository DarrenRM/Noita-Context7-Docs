---
title: Roadblock Biome Configuration
category: biome
---

# Roadblock Biome Configuration

This document details the configuration for the "Roadblock" biome in Noita, focusing on its generation parameters and material distribution.

## Topology Settings

The `Topology` element defines the fundamental generation characteristics of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`type`**: `BIOME_WANG_TILE` - Specifies the biome generation method.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - The background image used for this biome.
*   **`lua_script`**: `data/scripts/biomes/roadblock.lua` - The associated Lua script that further defines biome behavior.
*   **`mBiomeMaterialsFile`**: `data/materials/biome_forest.xml` - References a material file, likely for shared material properties.
*   **`mExtraPerlinScaleX`, `mExtraPerlinScaleY`**: Controls the scaling of additional Perlin noise for terrain variation.
*   **`mGradientAddNoise`, `mGradientHighNoise`, `mGradientLowNoise`, `mGradientNoiseScale`**: Parameters for adding and shaping noise within the biome's gradient.
*   **`mGradientMaxY`, `mGradientMinY`, `mGradientStartY`, `mGradientEndY`**: Define the vertical range and behavior of the biome's gradient.
*   **`mGradientType`**: `1` - Specifies the type of gradient used.
*   **`mInsidePerlinScaleMax`, `mInsidePerlinScaleMin`, `mInsidePerlinScaleX`, `mInsidePerlinScaleY`**: Control the scaling and application of Perlin noise within the biome's core generation.
*   **`mMultiplierGradient`, `mMultiplierPerlin`**: Factors that influence the overall impact of gradient and Perlin noise on the terrain.
*   **`mPerlinScale_x`, `mPerlinScale_y`**: Base scaling for Perlin noise in the X and Y directions.
*   **`mWaterLevel`**: `1000` - Sets the default water level for this biome.
*   **`coarse_map_not_terrain`**: `1` - Indicates that the coarse map does not directly define terrain.
*   **`coarse_map_cell_count_always_zero`**: `1` - Suggests a specific behavior for cell counts in the coarse map.

## Material Distribution

The `Materials` element defines how different materials are distributed within the biome.

### Key Material Components:

The following table summarizes the key `MaterialComponent` elements and their primary attributes.

| Material Name      | `is_rare` | `limit_min_y` | `limit_max_y` | `material_max` | `material_min` | `rare_use_polka` | `rare_polka_probability` |
| :----------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :--------------- | :----------------------- |
| `coal`             | `1`       | `100`         | `2048`        | `0.55`         | `0.51`         | `1`              | `0.160871`               |
| `rock_hard`        | `0`       | `100`         | `2048`        | `0.95`         | `-100.0`       | `1`              | `0.2`                    |
| `coal`             | `1`       | `100`         | `2048`        | `1.2`          | `1.1`          | `1`              | `0.157143`               |
| `copper`           | `1`       | `750`         | `2048`        | `1.25`         | `1.05`         | `1`              | `0.357143`               |
| `rock_hard_border` | `0`       | `100`         | `2048`        | `3.5`          | `-0.25`        | `1`              | `0.2`                    |

### Notable Attributes within `MaterialComponent`:

*   **`material_name`**: The name of the material being distributed (e.g., `coal`, `rock_hard`, `copper`).
*   **`is_rare`**: `1` indicates the material is less common, `0` for more common.
*   **`limit_min_y`, `limit_max_y`**: Vertical bounds within which the material can appear.
*   **`material_max`, `material_min`**: Define the range of values that determine the material's presence and density.
*   **`rare_use_polka`**: `1` indicates that a "polka" distribution pattern is used for rare materials, influencing their clustering.
*   **`rare_polka_probability`**: The likelihood of the rare material appearing in a given area.
*   **`rare_polka_radius_high`, `rare_polka_radius_low`**: Control the size and spread of clusters for rare materials.
*   **`rare_scale_x`, `rare_scale_y`**: Scaling factors for noise applied to rare material distribution.
*   **`rare_use_perlin`**: `1` indicates Perlin noise is used to influence the distribution of this rare material.