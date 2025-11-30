---
title: Lava Biome Configuration
category: biome
---

# Lava Biome Configuration

This document details the configuration for a lava-themed biome in Noita, focusing on its procedural generation and material properties.

## Topology

The `<Topology>` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes:

*   **`name`**: `$biome_lava` - A unique identifier for this biome.
*   **`type`**: `BIOME_PROCEDURAL` - Indicates that the biome is generated procedurally.
*   **`background_image`**: `data/weather_gfx/background_cave_04.png` - The primary background texture for the biome.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: These attributes specify textures for the edges of the background, creating a more cohesive visual.
*   **`background_edge_priority`**: `9` - Determines the rendering order of background edges. Higher values are drawn on top.
*   **`lua_script`**: `data/scripts/biomes/hills.lua` - A Lua script that likely controls procedural generation logic or specific biome behaviors.
*   **`noise_biome_edges`**: `0` - Disables noise-based generation for biome edges.
*   **`skip_edge_textures`**: `1` - Skips the application of standard edge textures, relying on the specified background edge images.

## Materials

The `<Materials>` element defines the types of materials present within the biome and their generation parameters.

### Material Component: Lava

This section configures the "lava" material.

#### Key Attributes:

*   **`name`**: `lava` - The name of the material component.
*   **`is_rare`**: `0` - Indicates that this material is not considered rare.
*   **`limit_max_y`**: `2048` - The maximum Y-coordinate (height) at which this material can appear.
*   **`limit_min_y`**: `100` - The minimum Y-coordinate (height) at which this material can appear.
*   **`limit_y`**: `0` - This attribute's purpose is less clear without further context, but it's set to 0.
*   **`material_index`**: `10` - A numerical index for this material, likely used internally by the game.
*   **`material_max`**: `100` - The maximum density or prevalence of this material.
*   **`material_min`**: `-100` - The minimum density or prevalence of this material.
*   **`material_name`**: `lava` - The in-game name of the material.
*   **`rare_polka_probability`**: `0.160871` - Probability related to a "polka" effect, likely for rare variations.
*   **`rare_polka_radius_high`**: `0.771429` - Controls the radius of the "polka" effect.
*   **`rare_polka_radius_low`**: `0.357143` - Controls the lower bound of the "polka" effect radius.
*   **`rare_required_max`**: `10` - Maximum requirement for a rare variant.
*   **`rare_required_min`**: `0` - Minimum requirement for a rare variant.
*   **`rare_scale_x`**: `0.0100004` - Scaling factor for rare variations in the X-axis.
*   **`rare_scale_y`**: `0.00357165` - Scaling factor for rare variations in the Y-axis.
*   **`rare_use_perlin`**: `0` - Disables Perlin noise for rare variations.
*   **`rare_use_polka`**: `0` - Disables the "polka" effect for rare variations.
*   **`is_polygon`**: `1` - Indicates that the material's shape is defined by a polygon.

#### Polygon Definition:

The `<polygon>` element defines the shape of the material.

*   **`Vec2`**: Defines points within the polygon. The provided points `(0, 0.02)`, `(1, 0.02)`, `(1, 1)`, and `(0, 1)` suggest a rectangular shape that covers most of the available space, offset slightly from the bottom.