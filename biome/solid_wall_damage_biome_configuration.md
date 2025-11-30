---
title: Solid Wall Damage Biome Configuration
category: biome
---

# Solid Wall Damage Biome Configuration

This document details the configuration for the "solid_wall_damage" biome in Noita, focusing on how it defines the generation and properties of solid walls within the game.

## Topology Settings

The `<Topology>` tag defines the overall structure and generation parameters for the biome.

### Key Attributes:

*   **`name`**: "_EMPTY_" - Indicates this topology is a base or placeholder.
*   **`background_image`**: "data/weather_gfx/background_cave_02.png" - Specifies the background visual for this biome.
*   **`lua_script`**: "data/scripts/biomes/solid_wall_tower.lua" - Links to a Lua script that likely controls more complex biome generation logic.
*   **`mBiomeMaterialsFile`**: "data/materials/biome_forest.xml" - References a file defining the base materials used in this biome.
*   **`mGradientEndY`, `mGradientStartY`**: Define the vertical range for gradient-based generation.
*   **`mGradientType`**: "1" - Specifies the type of gradient used for terrain generation.
*   **`mPerlinScale_x`, `mPerlinScale_y`**: Control the scaling of Perlin noise for terrain features.
*   **`mWaterLevel`**: "1000" - Sets the default water level within the biome.

## Material Components

The `<Materials>` tag and its nested `<MaterialComponent>` tags define the specific materials that make up the solid walls and their distribution.

### Key Attributes for `MaterialComponent`:

*   **`name`**: "solid_wall" - Identifies this set of components as belonging to the solid wall material group.
*   **`material_name`**: The name of the material (e.g., "coal", "rock_hard", "copper").
*   **`material_index`**: An internal index for the material.
*   **`material_min`, `material_max`**: Define the range of values for this material's density or presence.
*   **`limit_min_y`, `limit_max_y`**: Specify the vertical range where this material can appear.
*   **`is_rare`**: "1" or "0" - Indicates if the material is considered rare within this biome.
*   **`rare_polka_probability`**: Controls the likelihood of this rare material appearing.
*   **`rare_polka_radius_low`, `rare_polka_radius_high`**: Define the spatial distribution radius for rare materials.
*   **`rare_use_perlin`**: "1" or "0" - Whether Perlin noise influences the distribution of this rare material.
*   **`rare_use_polka`**: "1" or "0" - Whether a "polka" distribution pattern is used for rare materials.

### Material Breakdown:

| Material Name      | `is_rare` | `limit_min_y` | `limit_max_y` | `material_min` | `material_max` | `rare_polka_probability` | Notes                                                                 |
| :----------------- | :-------- | :------------ | :------------ | :------------- | :------------- | :----------------------- | :-------------------------------------------------------------------- |
| `coal`             | 1         | 100           | 2048          | 0.51           | 0.55           | 0.160871                 | Appears as a rare component, likely for visual variation.             |
| `rock_hard`        | 0         | 100           | 2048          | -100.0         | 0.95           | 0.2                      | The primary component of solid walls, with a wide value range.        |
| `coal`             | 1         | 100           | 2048          | 1.1            | 1.2            | 0.157143                 | Another instance of coal, potentially with different distribution.    |
| `copper`           | 1         | 750           | 2048          | 1.05           | 1.25           | 0.357143                 | A rarer copper deposit found at higher elevations.                    |
| `rock_hard_border` | 0         | 100           | 2048          | -0.25          | 3.5            | 0.2                      | Used for the outer edges or borders of solid wall structures.         |

**Note:** The `_EMPTY_` topology name and the `lua_script` suggest that the actual generation of this biome might be heavily influenced by external scripts, with this XML file primarily defining material compositions and some basic generation parameters.