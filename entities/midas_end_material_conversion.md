---
title: Midas End Material Conversion
category: entities
---

---

# Midas End Material Conversion

This entity defines a material conversion effect, likely used in a trailer or specific in-game event. It transforms surrounding materials into gold.

## MagicConvertMaterialComponent

This component handles the material conversion logic.

### Key Attributes:

*   **`kill_when_finished`**: `1` - The entity will be removed once the conversion process is complete.
*   **`convert_entities`**: `1` - This will also convert any entities within the conversion radius.
*   **`steps_per_frame`**: `3` - Controls the smoothness and speed of the conversion effect. Higher values mean faster conversion.
*   **`to_material`**: `"gold_b2"` - The target material that will replace existing materials.
*   **`clean_stains`**: `0` - Stains will not be cleaned during the conversion.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `320` - The radius in pixels within which materials will be converted.