---
title: Moon Effect - Drunk
category: entities
---

# Moon Effect - Drunk

This entity defines a special effect that occurs during the "drunk" moon phase in Noita. It primarily utilizes a `MagicConvertMaterialComponent` to transform nearby materials into "alcohol".

## Key Components

### MagicConvertMaterialComponent

This component is responsible for the material transformation effect.

*   **`to_material`**: `alcohol` - Specifies that the target material for conversion is alcohol.
*   **`radius`**: `300` - The area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - Controls the rate at which material conversion occurs.
*   **`from_any_material`**: `1` - Indicates that this effect can convert any material it encounters.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`kill_when_finished`**: `0` - The effect does not automatically despawn after its duration.
*   **`clean_stains`**: `0` - This effect does not clean existing stains.

### LifetimeComponent

This component dictates how long the effect persists.

*   **`lifetime`**: `160` - The duration of the effect in game frames.