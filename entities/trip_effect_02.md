---
title: Trip Effect 02
category: entities
---

# Trip Effect 02

This entity defines a visual and auditory "trip" effect in Noita, likely triggered by specific in-game events or items.

## Key Components

### GameEffectComponent
This component manages the overall duration and type of the game effect.

*   **`effect`**: `CUSTOM` - Indicates a custom-defined effect.
*   **`custom_effect_id`**: `TRIP_00` - A unique identifier for this specific trip effect.
*   **`frames`**: `600` - The duration of the effect in game frames (approximately 10 seconds).

### DrugEffectModifierComponent
This component applies visual distortions and color modifications to the screen.

*   **`fx_add`**: This nested element defines the intensity of various visual effects.
    *   **`distortion_amount`**: `0.5` - Controls the strength of screen distortion.
    *   **`color_amount`**: `0.4` - Controls the intensity of color shifts and saturation.
    *   **`fractals_amount`**: `1.0` - Controls the intensity of fractal patterns overlayed on the screen.

## Tags

*   `music_energy_100`: This tag suggests the effect is associated with a high level of "music energy," potentially influencing the intensity or nature of the trip.