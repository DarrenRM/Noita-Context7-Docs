---
title: Robot Egg Biome Configuration
category: biome
---

---

# Robot Egg Biome Configuration

This document details the configuration for the "Robot Egg" biome in Noita, focusing on its visual and material properties.

## Topology

The `Topology` element defines the visual background and scripting for the biome.

### Key Attributes:

*   **`name`**: `_EMPTY_` - Indicates this is a base configuration, likely to be overridden or combined.
*   **`background_image`**: `data/weather_gfx/background_cave_01.png` - Specifies the primary background texture.
*   **`background_edge_left`, `background_edge_right`, `background_edge_top`, `background_edge_bottom`**: These attributes define the textures used for the edges of the biome background, creating a seamless transition.
*   **`background_edge_priority`**: `10` - Controls the rendering order of background edges. Higher values are drawn on top.
*   **`background_use_neighbor`**: `0` - Disables the use of neighbor biome textures for background blending.
*   **`lua_script`**: `data/scripts/biomes/robot_egg.lua` - The primary script governing the behavior and generation of this biome.
*   **`noise_biome_edges`**: `0` - Disables noise-based generation for biome edges.
*   **`skip_edge_textures`**: `1` - Prevents the application of standard edge textures, likely relying on custom ones defined elsewhere or within the script.

## Materials

The `Materials` element defines the distribution and properties of different materials within the biome.

### Key Attributes for `Materials`:

*   **`name`**: `lava` - This indicates that the following `MaterialComponent` is related to the "lava" material type.

### `MaterialComponent` Details:

This section configures how the "lava" material is distributed and its characteristics within the biome.

*   **`_enabled`**: `1` - The component is active.
*   **`is_rare`**: `0` - This material component is not considered rare.
*   **`limit_max_y`**: `2048` - The maximum Y-coordinate (height) at which this material can appear.
*   **`limit_min_y`**: `100` - The minimum Y-coordinate (height) at which this material can appear.
*   **`limit_y`**: `0` - This attribute's effect is unclear without further context, but it's set to 0.
*   **`material_index`**: `10` - A numerical identifier for this material component.
*   **`material_max`**: `100` - The maximum density or concentration of this material.
*   **`material_min`**: `-100` - The minimum density or concentration of this material.
*   **`material_name`**: `lava` - Explicitly names the material being configured.
*   **`rare_polka_is_boxed`**: `0` - Controls a specific rare distribution pattern.
*   **`rare_polka_probability`**: `0.160871` - The probability of the "polka" distribution pattern occurring.
*   **`rare_polka_radius_high`**: `0.771429` - The upper bound for the radius of the "polka" distribution.
*   **`rare_polka_radius_low`**: `0.357143` - The lower bound for the radius of the "polka" distribution.
*   **`rare_required_max`**: `10` - The maximum requirement for a condition related to rare distribution.
*   **`rare_required_min`**: `0` - The minimum requirement for a condition related to rare distribution.
*   **`rare_scale_x`**: `0.0100004` - The scaling factor for the "polka" distribution along the X-axis.
*   **`rare_scale_y`**: `0.00357165` - The scaling factor for the "polka" distribution along the Y-axis.
*   **`rare_use_perlin`**: `0` - Disables Perlin noise for rare distribution.
*   **`rare_use_polka`**: `0` - Disables the "polka" distribution pattern for this material component.

**Note:** Many of the `rare_` attributes are set to `0` or default values, suggesting that the primary distribution of "lava" in this biome is not governed by these specific rare patterns. The `lua_script` is likely responsible for more nuanced material placement.