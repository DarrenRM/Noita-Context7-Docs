---
title: Material Converter (Freeze)
category: entities
---

# Material Converter (Freeze)

This entity acts as a localized material converter, specifically designed to freeze liquids and extinguish fires within its radius.

## Key Components

### `MagicConvertMaterialComponent`

This component defines the core functionality of the material conversion.

*   **`from_material_array`**: A comma-separated list of materials that this converter will target.
    *   `water`
    *   `water_ice`
    *   `water_salt`
    *   `water_fading`
    *   `water_static`
    *   `fire`
    *   `lava`
    *   `water_swamp`
    *   `radioactive_liquid`
    *   `acid`
    *   `blood_cold`
    *   `blood`
    *   `poison`
    *   `slime`
    *   `radioactive_liquid_fading`
*   **`to_material_array`**: A comma-separated list of materials that the `from_material_array` materials will be converted into. The order corresponds directly to the `from_material_array`.
    *   `ice_static` (for most water types)
    *   `air` (for fire)
    *   `rock_static` (for lava)
    *   `ice_radioactive_static` (for radioactive liquids)
    *   `ice_acid_static` (for acid)
    *   `ice_cold_static` (for blood_cold)
    *   `ice_blood_static` (for blood)
    *   `ice_poison_static` (for poison)
    *   `ice_slime_static` (for slime)
*   **`kill_when_finished`**: Set to `0`, meaning the converter does not disappear after its conversion cycle.
*   **`steps_per_frame`**: Set to `5`, indicating how many conversion steps occur per game frame.
*   **`is_circle`**: Set to `1`, meaning the conversion area is circular.
*   **`radius`**: Set to `72`, defining the radius of the circular conversion area.
*   **`extinguish_fire`**: Set to `1` in the second component, explicitly ensuring that any fires within the radius are extinguished. This is a more direct way to handle fire than relying solely on the `from_material_array` conversion.