---
title: Gold Biome Configuration
category: biome
---

# Gold Biome Configuration

This document details the configuration for the Gold biome in Noita, focusing on its procedural generation and material composition.

## Topology

The `Topology` element defines the fundamental structure and visual aspects of the biome.

### Key Attributes

*   **`name`**: `$biome_gold` - The internal identifier for this biome.
*   **`type`**: `BIOME_PROCEDURAL` - Indicates that this biome is generated procedurally.
*   **`background_image`**: `data/weather_gfx/background_cave_04.png` - Specifies the background visual asset for this biome.

## Materials

The `Materials` element governs the distribution and properties of different materials within the biome.

### Material Components

This section details the specific material components that make up the Gold biome.

#### Gold Material Component

*   **`name`**: `water` - This seems to be a placeholder or a general category name, as the `material_name` attribute specifies "gold".
*   **`material_name`**: `gold` - The primary material being configured.
*   **`material_index`**: `10` - An internal index for the material.
*   **`material_max`**: `100` - The maximum concentration or density of this material.
*   **`material_min`**: `-100` - The minimum concentration or density of this material.
*   **`limit_min_y`**: `100` - The minimum Y-coordinate (height) at which this material can appear.
*   **`limit_max_y`**: `2048` - The maximum Y-coordinate (height) at which this material can appear.
*   **`is_rare`**: `0` - Indicates that this material is not considered rare.
*   **`rare_use_polka`**: `0` - Disables a specific "polka" distribution pattern for this material.
*   **`rare_polka_probability`**: `0.160871` - The probability of the "polka" pattern appearing (though disabled).
*   **`rare_polka_radius_low`**: `0.357143` - The lower bound for the radius of the "polka" pattern (though disabled).
*   **`rare_polka_radius_high`**: `0.771429` - The upper bound for the radius of the "polka" pattern (though disabled).
*   **`rare_scale_x`**: `0.0100004` - The scaling factor for the X-axis of the "polka" pattern (though disabled).
*   **`rare_scale_y`**: `0.00357165` - The scaling factor for the Y-axis of the "polka" pattern (though disabled).