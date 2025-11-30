---
title: Sauna Stove Heat Entity
category: entities
---

# Sauna Stove Heat Entity

This entity defines the behavior of a "sauna stove" that generates heat and converts liquids into gases.

## Key Components

### MagicConvertMaterialComponent

This component handles the conversion of specific materials into others when the entity is active.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `_tags`             | Determines when the component is active (`enabled_in_hand`, `enabled_in_world`).                        |
| `from_material_array` | An array of materials that will be converted (e.g., `water`, `water_swamp`).                          |
| `to_material_array` | An array of materials that the `from_material_array` will be converted into (e.g., `steam`, `radioactive_gas`). |
| `kill_when_finished`| If set to `1`, the entity is removed after conversion is complete. `0` means it persists.              |
| `steps_per_frame`   | Controls the number of conversion steps performed each frame, affecting conversion speed.               |
| `clean_stains`      | If `1`, this component will also clean stains in the area. `0` means it does not.                       |
| `is_circle`         | If `1`, the conversion area is circular. If `0`, it's rectangular.                                      |
| `radius`            | The radius of the conversion area when `is_circle` is `1`.                                              |
| `reaction_audio_amount` | Controls the intensity of the audio played during the material conversion.                              |