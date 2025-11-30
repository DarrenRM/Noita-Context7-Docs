---
title: Effect Trip 03 (Extreme Tripping)
category: entities
---

# Effect Trip 03 (Extreme Tripping)

This entity defines an extreme tripping effect, likely a powerful status effect in Noita. It combines visual distortions, a food poisoning debuff, and custom Lua scripting for more complex behavior.

## Key Components

### `GameEffectComponent` (x2)

This component applies various game effects.

*   **First Instance:**
    *   `effect="CUSTOM"`: Indicates a custom effect.
    *   `custom_effect_id="TRIP_00"`: A specific identifier for this custom effect.
    *   `frames="600"`: The duration of this effect in frames (10 seconds at 60 FPS).
*   **Second Instance:**
    *   `effect="FOOD_POISONING"`: Applies the standard food poisoning debuff.
    *   `frames="600"`: The duration of the food poisoning effect.

### `DrugEffectModifierComponent`

This component modifies the visual and perceptual aspects of the player, simulating a strong hallucinogenic state.

*   **`fx_add`:** Defines the intensity of various visual distortions.
    *   `distortion_amount="0.2"`: Moderate visual warping.
    *   `color_amount="1.5"`: Significant enhancement of color saturation and intensity.
    *   `fractals_amount="1.5"`: Strong fractal patterns overlaying the screen.
    *   `fractals_size="1.0"`: Standard size for the fractal patterns.

### `LuaComponent`

This component integrates custom Lua scripting to further define the behavior of the tripping effect.

*   `execute_every_n_frame="600"`: The script will execute its logic every 600 frames (10 seconds).
*   `script_source_file="data/scripts/status_effects/effect_trip_03.lua"`: Points to the external Lua script that contains the detailed logic for this effect. This script is crucial for understanding the full behavior beyond the XML definition.