---
title: Area Damage Entity
category: entities
---

# Area Damage Entity

This entity defines a persistent area that deals damage to entities within its radius. It's commonly used for environmental hazards or effects that persist over time.

## Key Components

### AreaDamageComponent

This is the core component responsible for the damage-dealing functionality.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `aabb_min.x`        | Minimum X-coordinate of the bounding box.                                                               |
| `aabb_min.y`        | Minimum Y-coordinate of the bounding box.                                                               |
| `aabb_max.x`        | Maximum X-coordinate of the bounding box.                                                               |
| `aabb_max.y`        | Maximum Y-coordinate of the bounding box.                                                               |
| `damage_per_frame`  | The amount of damage dealt to entities within the area each frame.                                      |
| `update_every_n_frame` | How often the damage check and application occurs (e.g., `1` means every frame).                        |
| `entities_with_tag` | A comma-separated list of tags. Only entities with these tags will be affected by the damage.           |
| `death_cause`       | A localization key or string defining the cause of death for entities killed by this area.              |
| `damage_type`       | The type of damage dealt (e.g., `DAMAGE_PROJECTILE`, `DAMAGE_MELEE`).                                  |
| `circle_radius`     | The radius of the circular area that deals damage.                                                      |

### SpriteComponent

This component handles the visual representation of the area damage entity.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `_enabled`          | Whether the sprite is enabled (`1` for enabled, `0` for disabled).                                      |
| `alpha`             | The transparency of the sprite (0.0 to 1.0).                                                            |
| `image_file`        | The path to the image file used for the sprite.                                                         |
| `offset_x`          | Horizontal offset of the sprite from the entity's origin.                                               |
| `offset_y`          | Vertical offset of the sprite from the entity's origin.                                                 |
| `rect_animation`    | Defines the animation state for the sprite (e.g., `spawn`, `idle`).                                   |
| `z_index`           | Determines the rendering order of the sprite. Higher values are rendered on top.                        |
| `never_ragdollify_on_death` | Prevents the entity from ragdolling when it dies.                                                   |

## Example Usage

This entity can be placed in the game world to create persistent damage zones. For example, a lava pool or a magical curse area. The `entities_with_tag` attribute is crucial for targeting specific types of entities.