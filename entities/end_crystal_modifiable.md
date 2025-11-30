---
title: End Crystal (Modifiable)
category: entities
---

# End Crystal (Modifiable)

This entity represents a modifiable End Crystal, a building entity in Noita. It primarily defines its hitbox.

## Key Attributes

### HitboxComponent
This component defines the physical boundaries of the End Crystal.

| Attribute   | Value   | Description                               |
| :---------- | :------ | :---------------------------------------- |
| `aabb_min_x` | -256    | Minimum X-coordinate of the bounding box. |
| `aabb_max_x` | 256     | Maximum X-coordinate of the bounding box. |
| `aabb_min_y` | -320    | Minimum Y-coordinate of the bounding box. |
| `aabb_max_y` | 206     | Maximum Y-coordinate of the bounding box. |

### Tags
The `workshop` tag indicates this entity is intended for use within the Noita workshop or modding environment.