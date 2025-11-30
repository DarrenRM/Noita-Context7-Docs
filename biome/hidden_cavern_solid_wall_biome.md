---
title: Hidden Cavern Solid Wall Biome
category: biome
---

# Hidden Cavern Solid Wall Biome

This document describes the configuration for the "solid_wall_hidden_cavern" biome in Noita, focusing on its generation parameters and material distribution.

## Topology

The `Topology` element defines the fundamental generation characteristics of the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background visual for this biome.
*   **`lua_script`**: `data/scripts/biomes/solid_wall_hidden_cavern.lua` - Links to the script that governs biome-specific behaviors.
*   **`mGradientEndY` / `mGradientStartY`**: Defines the vertical range for gradient-based generation.
*   **`mGradientHighNoise` / `mGradientLowNoise`**: Controls the intensity and range of noise applied to the gradient.
*   **`mGradientMaxY` / `mGradientMinY`**: Sets the Y-axis limits for the gradient's influence.
*   **`mGradientType`**: `1` - Specifies the type of gradient used for generation.
*   **`mInsidePerlinScaleX` / `mInsidePerlinScaleY`**: Controls the scaling of Perlin noise within the biome.
*   **`mMultiplierGradient` / `mMultiplierPerlin`**: Adjusts the overall influence of gradient and Perlin noise on the biome's structure.
*   **`mWaterLevel`**: `1000` - Sets the default water level for this biome.

## Materials

The `Materials` element defines the types and distribution of materials within the biome.

### Key Attributes:

*   **`name`**: `solid_wall` - Identifies this material set as the "solid wall" type.

### Material Components:

Each `MaterialComponent` defines a specific material and its properties within the biome.

#### `coal` (Rare)

*   **`material_name`**: `coal`
*   **`is_rare`**: `1`
*   **`limit_max_y` / `limit_min_y`**: Defines the vertical distribution range.
*   **`material_max` / `material_min`**: Controls the density and range of the material.
*   **`rare_polka_probability`**: `0.160871` - Probability of this rare material appearing.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling for the noise pattern used for distribution.
*   **`rare_use_polka`**: `1` - Indicates that a polka noise pattern is used for distribution.

#### `rock_hard` (Common)

*   **`material_name`**: `rock_hard`
*   **`is_rare`**: `0`
*   **`limit_max_y` / `limit_min_y`**: Defines the vertical distribution range.
*   **`material_max` / `material_min`**: Controls the density and range of the material.
*   **`rare_polka_is_boxed`**: `1` - Suggests a bounded distribution for this material.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling for the noise pattern used for distribution.
*   **`rare_use_polka`**: `1` - Indicates that a polka noise pattern is used for distribution.

#### `coal` (Rare, different distribution)

*   **`material_name`**: `coal`
*   **`is_rare`**: `1`
*   **`limit_max_y` / `limit_min_y`**: Defines the vertical distribution range.
*   **`material_max` / `material_min`**: Controls the density and range of the material.
*   **`rare_polka_probability`**: `0.157143` - Probability of this rare material appearing.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling for the noise pattern used for distribution.
*   **`rare_use_perlin`**: `1` - Indicates Perlin noise is used in conjunction with polka.
*   **`rare_use_polka`**: `1` - Indicates that a polka noise pattern is used for distribution.

#### `copper` (Rare)

*   **`material_name`**: `copper`
*   **`is_rare`**: `1`
*   **`limit_max_y` / `limit_min_y`**: Defines the vertical distribution range.
*   **`material_max` / `material_min`**: Controls the density and range of the material.
*   **`rare_polka_probability`**: `0.357143` - Probability of this rare material appearing.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling for the noise pattern used for distribution.
*   **`rare_use_perlin`**: `1` - Indicates Perlin noise is used in conjunction with polka.
*   **`rare_use_polka`**: `1` - Indicates that a polka noise pattern is used for distribution.

#### `rock_hard_border` (Common)

*   **`material_name`**: `rock_hard_border`
*   **`is_rare`**: `0`
*   **`limit_max_y` / `limit_min_y`**: Defines the vertical distribution range.
*   **`material_max` / `material_min`**: Controls the density and range of the material.
*   **`rare_polka_is_boxed`**: `1` - Suggests a bounded distribution for this material.
*   **`rare_scale_x` / `rare_scale_y`**: Scaling for the noise pattern used for distribution.
*   **`rare_use_polka`**: `1` - Indicates that a polka noise pattern is used for distribution.