---
title: Water to Poison Conversion Entity
category: entities
---

# Water to Poison Conversion Entity

This entity defines a mechanism for converting various forms of water into poison. It utilizes the `MagicConvertMaterialComponent` to achieve this transformation.

## Key Components

### `MagicConvertMaterialComponent`

This component is responsible for the material conversion process. Multiple instances are used to handle different types of water.

| Attribute         | Description                                                                 |
| :---------------- | :-------------------------------------------------------------------------- |
| `kill_when_finished` | Determines if the entity should be removed after the conversion is complete. `0` means it persists. |
| `from_material`   | The material type that will be converted.                                   |
| `steps_per_frame` | Controls the speed of the conversion process. Higher values mean faster conversion. |
| `to_material`     | The material type that the `from_material` will be converted into.        |
| `clean_stains`    | If `0`, existing stains of the `from_material` will not be cleaned.         |
| `is_circle`       | If `1`, the conversion area is circular.                                    |
| `radius`          | The radius of the conversion area in pixels.                                |

## Material Conversions

The entity is configured to convert the following water-based materials into poison:

*   `water`
*   `water_ice`
*   `water_static`
*   `water_temp`
*   `water_swamp`
*   `water_salt`

All conversions are set to transform into `poison` with a radius of 32 pixels and a `steps_per_frame` of 3. The `kill_when_finished` is set to `0`, meaning the conversion effect will remain active.