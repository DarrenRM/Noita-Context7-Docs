---
title: Moon Effect Sun Entity
category: entities
---

# Moon Effect Sun Entity

This entity defines a special effect that converts nearby materials into fire. It's likely used for a celestial event or a specific in-game mechanic.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion effect.

*   **`to_material`**: `fire` - The material that other materials will be converted into.
*   **`radius`**: `300` - The radius around the entity within which the conversion occurs.
*   **`is_circle`**: `1` - The conversion area is a circle.
*   **`from_any_material`**: `1` - The effect will convert any material it encounters.
*   **`steps_per_frame`**: `3` - Controls the intensity or speed of the conversion process.
*   **`kill_when_finished`**: `0` - The entity does not disappear after the effect is complete.
*   **`clean_stains`**: `0` - Stains are not removed by this effect.

### LifetimeComponent

This component determines how long the entity persists.

*   **`lifetime`**: `160` - The entity will exist for 160 frames.