---
title: Fire Gas Perk
category: entities
---

---

# Fire Gas Perk

This entity defines a perk that converts gas materials into fire.

## Key Components

### MagicConvertMaterialComponent

This component handles the core functionality of converting one material to another.

*   **`from_material_tag`**: `"[gas]"` - Specifies that the component targets materials tagged as "gas".
*   **`to_material`**: `"fire"` - Indicates that the target material for conversion is "fire".
*   **`steps_per_frame`**: `48` - Controls the intensity or speed of the conversion process. Higher values mean faster conversion.
*   **`loop`**: `1` - Enables the conversion to repeat continuously.
*   **`is_circle`**: `1` - Defines the conversion area as a circle.
*   **`radius`**: `48` - Sets the radius of the circular conversion area.