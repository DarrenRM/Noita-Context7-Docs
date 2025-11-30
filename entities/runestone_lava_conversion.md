---
title: Runestone Lava Conversion
category: entities
---

# Runestone Lava Conversion

This entity defines a runestone that converts nearby liquids into lava.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion effect.

*   **`kill_when_finished`**: `1` - The entity will be removed once the conversion is complete.
*   **`from_material_tag`**: `[liquid]` - Specifies that any material tagged as `liquid` will be targeted for conversion.
*   **`steps_per_frame`**: `8` - The number of conversion steps to perform per game frame.
*   **`to_material`**: `lava` - The material that targeted liquids will be converted into.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `192` - The radius of the circular conversion area.
*   **`loop`**: `0` - The conversion effect does not loop.

### LifetimeComponent

This component determines how long the entity exists.

*   **`lifetime`**: `25` - The entity will exist for 25 game frames before being removed (if `kill_when_finished` is not already set to `1`).