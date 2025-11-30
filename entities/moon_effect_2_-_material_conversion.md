---
title: Moon Effect 2 - Material Conversion
category: entities
---

# Moon Effect 2 - Material Conversion

This entity defines a special effect that converts nearby materials into blood over time. It's likely used for a celestial or magical event within the game.

## Key Components

### MagicConvertMaterialComponent

This component handles the core functionality of material conversion.

*   **`to_material`**: `blood` - The target material that other materials will be converted into.
*   **`radius`**: `300` - The area of effect for the material conversion.
*   **`steps_per_frame`**: `3` - How many conversion steps occur each frame within the radius.
*   **`is_circle`**: `1` - The conversion area is a circle.
*   **`from_any_material`**: `1` - Any material within the radius will be converted.
*   **`kill_when_finished`**: `0` - The entity does not destroy itself after the conversion is complete.
*   **`clean_stains`**: `0` - Stains are not cleaned by this effect.

### LifetimeComponent

This component determines how long the effect persists.

*   **`lifetime`**: `160` - The duration of the effect in game frames.

## Summary

The `moon_effect2.xml` entity utilizes a `MagicConvertMaterialComponent` to transform any material within a 300-unit radius into `blood`. This conversion happens gradually over 160 frames, and the effect does not self-destruct upon completion.