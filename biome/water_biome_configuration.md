---
title: Water Biome Configuration
category: biome
---

# Water Biome Configuration

This document details the configuration for the "water" biome in Noita, focusing on its procedural generation and material properties.

## Topology

The `Topology` element defines the fundamental structure and appearance of the biome.

### Key Attributes

*   **`name`**: `$biome_water` - A unique identifier for this biome.
*   **`type`**: `BIOME_PROCEDURAL` - Indicates that this biome is generated procedurally.
*   **`background_image`**: `data/weather_gfx/background_cave_04.png` - Specifies the background visual asset for this biome.

## Materials

The `Materials` element governs the distribution and characteristics of materials within the biome.

### Material Component: Water

This section describes the primary material component for the water biome.

#### Key Attributes

*   **`name`**: `water` - The name of this material component.
*   **`_enabled`**: `1` - Ensures this component is active.
*   **`is_rare`**: `0` - This material is not considered rare.
*   **`limit_max_y`**: `2048` - The maximum Y-coordinate for this material's placement.
*   **`limit_min_y`**: `100` - The minimum Y-coordinate for this material's placement.
*   **`limit_y`**: `0` - A general Y-coordinate limit, often used in conjunction with min/max.
*   **`material_index`**: `10` - The internal index for the "water" material.
*   **`material_max`**: `100` - The maximum density or quantity of this material.
*   **`material_min`**: `-100` - The minimum density or quantity of this material.
*   **`material_name`**: `water` - The specific material being configured.
*   **`rare_polka_probability`**: `0.160871` - Probability related to a "polka" distribution pattern (if `rare_use_polka` were enabled).
*   **`rare_polka_radius_high`**: `0.771429` - High end of the radius for the "polka" distribution.
*   **`rare_polka_radius_low`**: `0.357143` - Low end of the radius for the "polka" distribution.
*   **`rare_required_max`**: `10` - Maximum requirement for a "rare" condition.
*   **`rare_required_min`**: `0` - Minimum requirement for a "rare" condition.
*   **`rare_scale_x`**: `0.0100004` - X-axis scaling factor for rare distribution.
*   **`rare_scale_y`**: `0.00357165` - Y-axis scaling factor for rare distribution.
*   **`rare_use_perlin`**: `0` - Disables Perlin noise for rare distribution.
*   **`rare_use_polka`**: `0` - Disables the "polka" distribution pattern for rare elements.