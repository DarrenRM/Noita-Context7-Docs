---
title: Mountain Left Entrance Biome
category: biome
---

# Mountain Left Entrance Biome

This document details the configuration for the "Mountain Left Entrance" biome in Noita, focusing on its terrain generation, material distribution, and visual elements.

## Topology

The `Topology` element defines the procedural generation of the biome's terrain.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base biome definition.
*   **`background_image`**: `data/weather_gfx/background_cave_02.png` - Specifies the background image used for this biome.
*   **`lua_script`**: `data/scripts/biomes/mountain/mountain_left_entrance.lua` - Links to a Lua script that can further customize biome generation.
*   **`noise_type`**: `SIN_CAPPED_SIMPLEX` - The type of noise algorithm used for terrain shaping.
*   **`mGradientAddNoise`**: `1` - Controls the addition of noise to the gradient.
*   **`mGradientEndY`**: `1024` - The Y-coordinate where the gradient ends.
*   **`mGradientHighNoise`**: `234.057` - The upper bound for gradient noise.
*   **`mGradientLowNoise`**: `-292.571` - The lower bound for gradient noise.
*   **`mGradientNoiseScale`**: `0.00128571` - Scales the noise applied to the gradient.
*   **`mGradientStartY`**: `-1024` - The Y-coordinate where the gradient starts.
*   **`mInsidePerlinScaleMax`**: `2` - Maximum scale for Perlin noise within the biome.
*   **`mInsidePerlinScaleMin`**: `0.057143` - Minimum scale for Perlin noise within the biome.
*   **`mMultiplierGradient`**: `0.871429` - A multiplier applied to the gradient.
*   **`audio_ambience`**: `temple` - The ambient soundscape associated with this biome.

## Materials

The `Materials` element defines the distribution and properties of various materials and vegetation within the biome.

### Material Components:

These components define how different materials are generated and their characteristics.

| Attribute                 | Value                               | Description                                                                 |
| :------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| **`name`**                | `mountain`                          | The name of this material set.                                              |
| **`_enabled`**            | `1`                                 | Whether this component is active.                                           |
| **`is_rare`**             | `0` or `1`                          | Indicates if the material is rare.                                          |
| **`limit_max_y`**         | Varies                              | Maximum Y-coordinate for material placement.                                |
| **`limit_min_y`**         | Varies                              | Minimum Y-coordinate for material placement.                                |
| **`limit_y`**             | `0` or `1`                          | Specific Y-coordinate limit.                                                |
| **`material_index`**      | `10`                                | Internal index for the material.                                            |
| **`material_max`**        | Varies                              | Maximum density/probability of the material.                                |
| **`material_min`**        | Varies                              | Minimum density/probability of the material.                                |
| **`material_name`**       | `coal`, `soil`, `rock_hard`, `rock_static` | The name of the material.                                                   |
| **`rare_polka_probability`** | Varies                              | Probability of "polka" pattern for rare materials.                          |
| **`rare_polka_radius_high`** | Varies                              | Upper radius for "polka" pattern.                                           |
| **`rare_polka_radius_low`**  | Varies                              | Lower radius for "polka" pattern.                                           |
| **`rare_scale_x`**        | Varies                              | X-axis scaling for rare material distribution.                              |
| **`rare_scale_y`**        | Varies                              | Y-axis scaling for rare material distribution.                              |
| **`rare_use_polka`**      | `1`                                 | Enables the "polka" distribution pattern for rare materials.                |

**Summary of Material Components:**

*   **Coal**: A rare material with specific Y-limits and a polka distribution pattern.
*   **Soil**: A common material with Y-limits and a polka distribution.
*   **Rock\_hard**: A common material with Y-limits and a polka distribution.
*   **Rock\_static**: A common material with Y-limits and a polka distribution.

### Vegetation Components:

These components define the placement and appearance of vegetation.

| Attribute             | Value                                       | Description                                                                 |
| :-------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| **`_enabled`**        | `1`                                         | Whether this component is active.                                           |
| **`is_visual`**       | `1`                                         | Indicates this is a visual element.                                         |
| **`rand_seed`**       | Varies                                      | Seed for random generation.                                                 |
| **`tree_material`**   | `grass`, `moss`, `ceiling_plant_material`, `plant_material` | The base material for the vegetation.                                       |
| **`tree_probability`**| Varies                                      | Probability of this vegetation appearing.                                   |
| **`tree_radius_high`**| Varies                                      | Upper radius for placement.                                                 |
| **`tree_radius_low`** | Varies                                      | Lower radius for placement.                                                 |
| **`tree_width`**      | Varies                                      | Width of the vegetation element.                                            |
| **`visual_color`**    | `0xffb89f6c`, `0x00b89f6c`, `0xff4d5d44`      | The color of the vegetation (RGBA format).                                  |
| **`visual_offset_x`** | Varies                                      | X-axis offset for visual placement.                                         |
| **`visual_offset_y`** | Varies                                      | Y-axis offset for visual placement.                                         |
| **`is_grass`**        | `1`                                         | Marks this as grass.                                                        |
| **`grass_requires_neighbors`** | `0` or `1`                          | Whether grass requires adjacent tiles.                                      |
| **`material_on_top_of`** | `soil`, `sand_static`                   | The material this vegetation can grow on.                                   |
| **`is_ceiling_plant`**| `1`                                         | Marks this as a plant growing from the ceiling.                             |
| **`tree_image_file`** | `data/vegetation/vine_growth_1.xml`, `data/vegetation/ceiling_vegetation_00$[2-8].png`, `data/vegetation/bush_growth_$[1-8].xml` | Path to the visual asset for the vegetation.                                |

**Summary of Vegetation Components:**

*   **Grass**: Appears on `soil` and `sand_static`, with varying neighbor requirements.
*   **Ceiling Plants**: Includes vine growth and other ceiling vegetation, with specific image files and probabilities.
*   **Bushes**: Appear with a specific image file pattern and color.