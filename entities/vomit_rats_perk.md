---
title: Vomit Rats Perk
category: entities
---

# Vomit Rats Perk

This entity defines the "Vomit Rats" perk in Noita. When this perk is active, certain materials are converted into "rat powder" in a circular area around the player.

## Key Components

### MagicConvertMaterialComponent

This component handles the material conversion effect. The "Vomit Rats" perk utilizes two instances of this component to convert different materials.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `from_material`  | The material to be converted.                                               |
| `to_material`    | The material that the `from_material` will be converted into.               |
| `steps_per_frame`| How many conversion steps are performed each frame. Higher values mean faster conversion. |
| `loop`           | If set to `1`, the conversion effect will continuously repeat.              |
| `is_circle`      | If set to `1`, the conversion occurs in a circular area.                    |
| `radius`         | The radius of the circular area where the material conversion takes place.  |

#### Instance 1: Vomit to Rat Powder

*   `from_material`: `vomit`
*   `to_material`: `rat_powder`
*   `steps_per_frame`: `20`
*   `loop`: `1`
*   `is_circle`: `1`
*   `radius`: `20`

#### Instance 2: Urine to Rat Powder

*   `from_material`: `urine`
*   `to_material`: `rat_powder`
*   `steps_per_frame`: `20`
*   `loop`: `1`
*   `is_circle`: `1`
*   `radius`: `20`