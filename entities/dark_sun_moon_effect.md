---
title: Dark Sun Moon Effect
category: entities
---

# Dark Sun Moon Effect

This entity defines a special effect that transforms materials in its vicinity into "material_darkness". It's likely used as a visual or gameplay mechanic associated with a "dark sun" event or entity in Noita.

## Key Components

### MagicConvertMaterialComponent

This component is responsible for the material transformation effect.

*   **`to_material`**: `material_darkness` - Specifies the target material that existing materials will be converted into.
*   **`radius`**: `300` - The area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - Controls the speed or intensity of the conversion process.
*   **`is_circle`**: `1` - Indicates that the effect's area of influence is circular.
*   **`from_any_material`**: `1` - Allows the effect to convert any material it encounters.
*   **`kill_when_finished`**: `0` - The entity will persist after the conversion is complete, not self-destruct.
*   **`clean_stains`**: `0` - Stains are not removed by this effect.

### LifetimeComponent

This component dictates how long the effect will persist.

*   **`lifetime`**: `160` - The duration of the effect in game frames.