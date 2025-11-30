---
title: Friend 3 Biome Configuration
category: biome
---

# Friend 3 Biome Configuration

This document details the configuration for the "Friend 3" biome in Noita, focusing on its topological properties and material distribution.

## Topology

The `Topology` element defines the fundamental structure and visual characteristics of the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this is a base biome definition.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background image used for this biome.
*   **`lua_script`**: "data/scripts/biomes/friend_3.lua" - Links to the biome's associated Lua script for dynamic behavior.
*   **`mBiomeMaterialsFile`**: "data/materials/biome_forest.xml" - References a file defining the general material set for this biome.
*   **`mGradientEndY`**, **`mGradientStartY`**: Define the vertical range for gradient-based effects.
*   **`mGradientType`**: "1" - Suggests a specific type of gradient generation.
*   **`mWaterLevel`**: "1000" - Sets the default water level within the biome.
*   **`mExtraPerlinScaleX`**, **`mExtraPerlinScaleY`**: Control the scale of additional Perlin noise for terrain variation.
*   **`mGradientHighNoise`**, **`mGradientLowNoise`**: Define the range of noise values applied to the gradient.

```xml
<Topology
  name="_EMPTY_"
  background_image="data/weather_gfx/background_cave_02.png"
  background_use_neighbor="0"
  lua_script="data/scripts/biomes/friend_3.lua"
  mBiomeMaterialsFile="data/materials/biome_forest.xml"
  mExtraPerlinScaleX="0.05"
  mExtraPerlinScaleY="0.0342857"
  mGradientAddNoise="1"
  mGradientEndY="1024"
  mGradientHighNoise="234.057"
  mGradientLowNoise="-292.571"
  mGradientMaxY="0.17"
  mGradientMinY="0.25"
  mGradientNoiseScale="0.00128571"
  mGradientSinMultipleMax="0.005153"
  mGradientSinMultipleMin="0.0021"
  mGradientStartY="-1024"
  mGradientType="1"
  mInsidePerlinClamped="0"
  mInsidePerlinScaleMax="2"
  mInsidePerlinScaleMin="0.057143"
  mInsidePerlinScaleX="1"
  mInsidePerlinScaleY="1"
  mInsidePerlinScaled="1"
  mInsidePerlinSquared="0"
  mMultiplierExtraPerlin="1"
  mMultiplierGradient="0.871429"
  mMultiplierPerlin="0.642857"
  mPerlinScale_x="0"
  mPerlinScale_y="105"
  mWaterLevel="1000"
  limit_background_image="1"
  fat_biome_edges="0"
  has_rain="0"
>
</Topology>
```

## Materials

The `Materials` element defines the types and distribution of materials within the biome. This section focuses on the `solid_wall` material type.

### `solid_wall` Material Components:

This section details various `MaterialComponent` entries that contribute to the `solid_wall` material. Each component specifies how a particular material (e.g., coal, rock\_hard, copper) is distributed and its properties within the biome.

#### Key Attributes for `MaterialComponent`:

*   **`material_name`**: The name of the material being added (e.g., "coal", "rock\_hard").
*   **`is_rare`**: Whether the material is considered rare within this component.
*   **`limit_max_y`**, **`limit_min_y`**: Vertical boundaries for the material's placement.
*   **`material_max`**, **`material_min`**: The range of values determining the material's density or presence.
*   **`rare_polka_probability`**: Probability of the material appearing in a "polka" pattern.
*   **`rare_scale_x`**, **`rare_scale_y`**: Scaling factors for the noise pattern used for rare material distribution.
*   **`rare_use_perlin`**, **`rare_use_polka`**: Flags to enable Perlin noise or polka distribution for rare materials.

#### Material Components for `solid_wall`:

| Material Name     | Is Rare | Min Y | Max Y | Min Value | Max Value | Polka Probability | Use Polka | Use Perlin |
| :---------------- | :------ | :---- | :---- | :-------- | :-------- | :---------------- | :-------- | :--------- |
| coal              | Yes     | 100   | 2048  | 0.51      | 0.55      | 0.160871          | Yes       | No         |
| rock\_hard        | No      | 100   | 2048  | -100.0    | 0.95      | 0.2               | Yes       | No         |
| coal              | Yes     | 100   | 2048  | 1.1       | 1.2       | 0.157143          | Yes       | Yes        |
| copper            | Yes     | 750   | 2048  | 1.05      | 1.25      | 0.357143          | Yes       | Yes        |
| rock\_hard\_border| No      | 100   | 2048  | -0.25     | 3.5       | 0.2               | Yes       | No         |

```xml
<Materials name="solid_wall">
  <MaterialComponent
    _enabled="1"
    is_rare="1"
    limit_max_y="2048"
    limit_min_y="100"
    limit_y="0"
    material_index="10"
    material_max="0.55"
    material_min="0.51"
    material_name="coal"
    rare_polka_is_boxed="0"
    rare_polka_probability="0.160871"
    rare_polka_radius_high="0.771429"
    rare_polka_radius_low="0.357143"
    rare_required_max="10"
    rare_required_min="0"
    rare_scale_x="0.0100004"
    rare_scale_y="0.00357165"
    rare_use_perlin="0"
    rare_use_polka="1" >
  </MaterialComponent>

  <MaterialComponent
    _enabled="1"
    is_rare="0"
    limit_max_y="2048"
    limit_min_y="100"
    limit_y="0"
    material_index="10"
    material_max="0.95"
    material_min="-100.0"
    material_name="rock_hard"
    rare_polka_is_boxed="1"
    rare_polka_probability="0.2"
    rare_polka_radius_high="0.65"
    rare_polka_radius_low="0.2"
    rare_required_max="10"
    rare_required_min="0.2"
    rare_scale_x="0.05"
    rare_scale_y="0.05"
    rare_use_perlin="0"
    rare_use_polka="1" >
  </MaterialComponent>

  <MaterialComponent
    _enabled="1"
    is_rare="1"
    limit_max_y="2048"
    limit_min_y="100"
    limit_y="0"
    material_index="10"
    material_max="1.2"
    material_min="1.1"
    material_name="coal"
    rare_polka_is_boxed="1"
    rare_polka_probability="0.157143"
    rare_polka_radius_high="0.464286"
    rare_polka_radius_low="0.0428571"
    rare_required_max="10"
    rare_required_min="0.371429"
    rare_scale_x="0.0214286"
    rare_scale_y="0.0214286"
    rare_use_perlin="1"
    rare_use_polka="1" >
  </MaterialComponent>

  <MaterialComponent
    _enabled="1"
    is_rare="1"
    limit_max_y="2048"
    limit_min_y="750"
    limit_y="1"
    material_index="10"
    material_max="1.25"
    material_min="1.05"
    material_name="copper"
    rare_polka_is_boxed="0"
    rare_polka_probability="0.357143"
    rare_polka_radius_high="0.764286"
    rare_polka_radius_low="0.328571"
    rare_required_max="10"
    rare_required_min="0.019"
    rare_scale_x="0.007514286"
    rare_scale_y="0.007514286"
    rare_use_perlin="1"
    rare_use_polka="1" >
  </MaterialComponent>

  <MaterialComponent
    _enabled="1"
    is_rare="0"
    limit_max_y="2048"
    limit_min_y="100"
    limit_y="0"
    material_index="9"
    material_max="3.5"
    material_min="-0.25"
    material_name="rock_hard_border"
    rare_polka_is_boxed="1"
    rare_polka_probability="0.2"
    rare_polka_radius_high="0.65"
    rare_polka_radius_low="0.2"
    rare_required_max="10"
    rare_required_min="0.2"
    rare_scale_x="0.05"
    rare_scale_y="0.05"
    rare_use_perlin="0"
    rare_use_polka="1" >
  </MaterialComponent>
</Materials>
```