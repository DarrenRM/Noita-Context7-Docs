---
title: Moon Effect Entity
category: entities
---

# Moon Effect Entity

This entity defines a special effect that converts materials within a radius into "void liquid" over time.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion process.

*   **`to_material`**: `void_liquid` - The material that existing materials will be converted into.
*   **`radius`**: `300` - The area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - How many conversion steps occur each frame.
*   **`is_circle`**: `1` - The conversion area is a circle.
*   **`from_any_material`**: `1` - The effect will convert any material it encounters.
*   **`kill_when_finished`**: `0` - The entity does not disappear after the conversion is complete.
*   **`clean_stains`**: `0` - Stains are not cleaned by this effect.

### LifetimeComponent

This component determines how long the entity persists.

*   **`lifetime`**: `160` - The entity will exist for 160 frames.