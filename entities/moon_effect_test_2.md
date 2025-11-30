---
title: Moon Effect Test 2
category: entities
---

# Moon Effect Test 2

This entity defines a special effect that converts materials within a radius to acid.

## Components

### MagicConvertMaterialComponent

This component handles the material conversion effect.

*   **`to_material`**: `acid` - The material that existing materials will be converted into.
*   **`radius`**: `300` - The radius around the entity where the conversion will occur.
*   **`steps_per_frame`**: `3` - How many conversion steps are performed per game frame.
*   **`from_any_material`**: `1` - Indicates that any material can be converted.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`kill_when_finished`**: `0` - The entity does not disappear after the effect is complete.
*   **`clean_stains`**: `0` - Stains are not cleaned by this effect.

### LifetimeComponent

This component defines how long the entity exists.

*   **`lifetime`**: `160` - The entity will exist for 160 game frames.