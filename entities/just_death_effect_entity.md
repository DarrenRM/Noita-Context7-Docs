---
title: Just Death Effect Entity
category: entities
---

# Just Death Effect Entity

This entity defines a special effect that converts materials into "just_death". It's likely used for specific game mechanics or spells that have a unique, instant-death-like effect.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion.

*   **`convert_entities`**: `1` - Indicates that this effect can convert entities, not just materials.
*   **`to_material`**: `"just_death"` - Specifies the target material for conversion.
*   **`steps_per_frame`**: `4` - Controls the intensity or speed of the conversion process.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `12` - The radius of the circular conversion area.

### LifetimeComponent

This component determines how long the effect persists.

*   **`lifetime`**: `3` - The effect will last for 3 game frames.