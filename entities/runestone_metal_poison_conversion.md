---
title: Runestone Metal (Poison Conversion)
category: entities
---

# Runestone Metal (Poison Conversion)

This entity defines a runestone that converts nearby meltable metals into poison.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion effect.

*   **`kill_when_finished`**: `1` - The entity will be removed once the conversion is complete.
*   **`from_material_tag`**:
    *   `[meltable_metal]`
    *   `[meltable_metal_generic]`
    These tags specify the types of materials that will be converted.
*   **`steps_per_frame`**: `8` - Controls the speed of the conversion process.
*   **`to_material`**: `poison` - The material that the targeted metals will be converted into.
*   **`clean_stains`**: `0` - Stains are not cleaned during the conversion.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `160` - The radius of the circular conversion area.
*   **`loop`**: `0` - The conversion effect does not loop.

### LifetimeComponent

*   **`lifetime`**: `25` - The entity will exist for 25 frames before being removed.