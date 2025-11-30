---
title: Green Crystal Effect
category: entities
---

# Green Crystal Effect

This entity defines a visual effect that transforms certain materials into smoke or cursed static when interacted with. It's likely used as a projectile or a spawned effect from another entity.

## Key Components

### MagicConvertMaterialComponent

This component is responsible for the material transformation. The entity has multiple instances of this component, each targeting different material tags.

*   **`kill_when_finished`**: `1` - The entity will be destroyed once the material conversion is complete.
*   **`steps_per_frame`**: `1` - Controls the speed of the conversion process.
*   **`clean_stains`**: `0` - Does not remove stains from the converted materials.
*   **`is_circle`**: `1` - The conversion area is circular.
*   **`radius`**: `100` - The radius of the circular conversion area.

#### Material Conversions

| `from_material_tag` | `to_material`       | Description                                                                 |
| :------------------ | :------------------ | :-------------------------------------------------------------------------- |
| `[liquid]`          | `smoke`             | Converts any liquid material to smoke.                                      |
| `[sand_other]`      | `smoke`             | Converts various sand-like materials to smoke.                              |
| `[sand_ground]`     | `smoke`             | Converts ground sand materials to smoke.                                    |
| `[static]`          | `rock_static_cursed` | Converts static materials to a cursed static variant.                       |