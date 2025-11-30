---
title: Gold Dust Chest Conversion
category: entities
---

# Gold Dust Chest Conversion

This entity defines a magical conversion process, likely used in conjunction with a chest that dispenses gold dust. When triggered, it transforms a specified material into gold.

## Key Components

### MagicConvertMaterialComponent

This component handles the material transformation.

*   **`kill_when_finished`**: `1` - The entity will be removed once the conversion is complete.
*   **`from_material`**: `"wood_prop"` - The material that will be converted.
*   **`steps_per_frame`**: `1` - Controls the speed of the conversion process.
*   **`to_material`**: `"gold"` - The material the `from_material` will be converted into.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `11` - The radius of the circular conversion area.