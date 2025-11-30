---
title: Holiday Mood Material Conversion
category: entities
---

# Holiday Mood Material Conversion

This entity defines a set of material conversion effects, primarily for creating a "holiday mood" by transforming various materials into snow or ice. It utilizes multiple `MagicConvertMaterialComponent` instances to achieve this.

## Key Components and Attributes

The core functionality is driven by the `MagicConvertMaterialComponent`. Here are the key attributes used:

### `MagicConvertMaterialComponent`

This component is responsible for converting one material into another within a specified radius.

| Attribute           | Description                                                                                                |
| :------------------ | :--------------------------------------------------------------------------------------------------------- |
| `kill_when_finished` | If set to `1`, the entity will be removed once the conversion process is complete.                         |
| `from_material_tag` | Specifies the tag of the material(s) to be converted. Examples include `[solid]`, `[sand_ground]`, `[liquid]`. |
| `steps_per_frame`   | Controls the speed of the conversion process. Higher values mean faster conversion.                        |
| `to_material`       | The target material that the `from_material_tag` will be converted into.                                   |
| `clean_stains`      | If set to `1`, any stains on the converted material will be removed.                                       |
| `is_circle`         | If set to `1`, the conversion area is a circle.                                                            |
| `radius`            | The radius (in pixels) around the entity where the material conversion will occur.                         |
| `loop`              | If set to `0`, the conversion happens once. If `1`, it would loop (though not used here).                  |

## Material Conversion Rules

The entity defines several rules for material conversion:

*   **Solid to Snow:**
    *   `from_material_tag`: `[solid]`
    *   `to_material`: `snow_static`
    *   `radius`: `512`

*   **Sand Ground to Snow:**
    *   `from_material_tag`: `[sand_ground]`
    *   `to_material`: `snow`
    *   `radius`: `512`

*   **Other Sand to Snow:**
    *   `from_material_tag`: `[sand_other]`
    *   `to_material`: `snow`
    *   `radius`: `512`

*   **Liquid to Ice:**
    *   `from_material_tag`: `[liquid]`
    *   `to_material`: `water_ice`
    *   `radius`: `512`

This setup effectively transforms a large circular area around the entity into a snowy or icy environment.