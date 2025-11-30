---
title: Bounce Hole Projectile
category: entities
---

# Bounce Hole Projectile

This entity defines a special projectile in Noita, the "Bounce Hole". It's designed to interact with the game world by consuming certain materials and leaving behind a visual effect.

## Key Attributes

### Entity
- **name**: `$projectile_default` (Indicates it uses default projectile properties)
- **tags**: `projectile_player` (Identifies it as a projectile fired by the player)

### Base Projectile
- **file**: `data/entities/base_projectile.xml` (Inherits core projectile functionality)

### Projectile Component
This component governs the projectile's behavior and properties.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `_enabled`                | `1`     | Enables this component.                                                     |
| `lob_min`, `lob_max`      | `0.8`, `1.0` | Controls the lobbing behavior (how much it arcs).                           |
| `speed_min`, `speed_max`  | `0`, `0` | Projectile has no initial speed, likely meaning it's spawned at a location. |
| `die_on_low_velocity`     | `0`     | Does not die if its velocity drops too low.                                 |
| `on_death_explode`        | `0`     | Does not explode upon death.                                                |
| `on_death_gfx_leave_sprite` | `0`     | Does not leave a sprite graphic upon death.                                 |
| `on_lifetime_out_explode` | `0`     | Does not explode when its lifetime expires.                                 |
| `explosion_dont_damage_shooter` | `0` | Does not prevent damage to the shooter if it were to explode.               |
| `on_collision_die`        | `0`     | Does not die upon collision.                                                |
| `shoot_light_flash_radius`| `15`    | Radius of the light flash when shot.                                        |
| `shoot_light_flash_r`     | `255`   | Red component of the shoot light flash color.                               |
| `shoot_light_flash_g`     | `10`    | Green component of the shoot light flash color.                             |
| `shoot_light_flash_b`     | `255`   | Blue component of the shoot light flash color.                              |
| `damage`                  | `0`     | Deals no damage.                                                            |
| `lifetime`                | `10`    | The projectile exists for 10 game frames.                                   |

### Cell Eater Component
This component allows the projectile to consume materials.

| Attribute           | Value                               | Description                                                                                             |
| :------------------ | :---------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `eat_probability`   | `35`                                | The chance (out of 100) that this projectile will eat a cell it encounters.                             |
| `radius`            | `8`                                 | The radius around the projectile within which it can eat cells.                                         |
| `ignored_material`  | `rock_static_cursed`                | This material will not be eaten by the projectile.                                                      |
| `ignored_material_tag` | `[matter_eater_ignore_list]` | A tag that can be used to group materials to be ignored by this component.                              |

### Variable Storage Component
- **name**: `projectile_file`
- **value_string**: `data/entities/projectiles/deck/bounce_hole.xml` (Stores the path to this entity's file, likely for internal referencing.)