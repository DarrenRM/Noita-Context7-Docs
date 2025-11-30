---
title: Boss Dragon (End Crystal) Entity
category: entities
---

# Boss Dragon (End Crystal) Entity

This document details the `boss_dragon_endcrystal.xml` entity, representing a boss dragon variant found in Noita. This entity is designed as a formidable opponent, likely encountered during specific game events or boss encounters.

## Core Components

### `BossDragonComponent`

This component governs the dragon's movement, targeting, and overall behavior as a boss entity.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `speed`                   | Base movement speed of the dragon.                                                                      |
| `speed_hunt`              | Increased movement speed when actively hunting a target.                                                |
| `acceleration`            | How quickly the dragon reaches its target speed.                                                        |
| `direction_adjust_speed`  | Speed at which the dragon adjusts its direction.                                                        |
| `direction_adjust_speed_hunt` | Increased speed for direction adjustments when hunting.                                                 |
| `tail_gravity`            | Affects the gravitational pull on the dragon's tail segments.                                           |
| `part_distance`           | The desired distance between connected body segments (e.g., tail segments).                             |
| `ground_check_offset`     | Offset used for ground detection.                                                                       |
| `hitbox_radius`           | The radius of the dragon's primary hitbox.                                                              |
| `target_kill_radius`      | Radius within which the dragon can instantly kill a target.                                             |
| `target_kill_ragdoll_force` | Force applied to ragdoll the target when killed instantly.                                              |
| `hunt_box_radius`         | Radius within which the dragon will actively hunt for targets.                                          |
| `random_target_box_radius`| Radius within which the dragon will search for random targets if no primary target is found.            |
| `new_hunt_target_check_every` | How often (in frames) the dragon checks for new hunt targets.                                           |
| `new_random_target_check_every` | How often (in frames) the dragon checks for new random targets.                                         |
| `ragdoll_filename`        | Path to the file defining the dragon's ragdoll structure.                                               |
| `jump_cam_shake`          | Intensity of camera shake when the dragon jumps.                                                        |

### `DamageModelComponent`

Manages the dragon's health and how it takes damage.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `hp`                      | Hit points of the dragon.                                                                               |
| `materials_damage`        | Whether the dragon takes damage from specific materials.                                                |
| `materials_how_much_damage` | The amount of damage taken from specified materials.                                                    |
| `materials_that_damage`   | List of materials that inflict damage on the dragon (e.g., "acid").                                     |
| `ragdoll_offset_y`        | Vertical offset for the ragdoll when it's created.                                                      |

### `GenomeDataComponent`

Defines the dragon's place in the game's ecosystem and its predatory nature.

| Attribute           | Description                                                                                             |
| :------------------ | :------------------------------------------------------------------------------------------------------ |
| `herd_id`           | Identifier for the dragon's herd or species.                                                            |
| `food_chain_rank`   | Its position in the food chain (higher means more dominant).                                            |
| `is_predator`       | Indicates if the entity is a predator.                                                                  |

## Visual Components (`SpriteComponent`)

The dragon is constructed from multiple sprite components, defining its head, body segments, and tail.

*   **Head Sprite:** `data/enemies_gfx/dragon_head.xml`
*   **Body Sprites:** Multiple instances of `data/enemies_gfx/dragon_body.xml`
*   **Tail Sprite:** `data/enemies_gfx/dragon_tail.xml`

Each sprite component has attributes like `image_file`, `rect_animation`, `offset_x`, `offset_y`, and `z_index` to control its appearance and layering. The `z_index` values suggest a layered structure for the dragon's body.

## Other Notable Components

*   **`CellEaterComponent`**: Suggests the dragon can consume certain entities or materials within a specified `radius`.
*   **`PathFindingGridMarkerComponent`**: Used for navigation and pathfinding within the game world.
*   **`BossHealthBarComponent`**: Likely responsible for displaying a boss-specific health bar.
*   **`LightComponent`**: Emits light with specified RGB values, contributing to the visual atmosphere.
*   **`LuaComponent` (Victory Script)**: `data/scripts/buildings/endcrystal_victory.lua` - This script is executed when the entity is removed, likely triggering victory conditions or related events.
*   **`LuaComponent` (Turret Projectile)**: Attached to an inherited entity, this component fires projectiles using `data/scripts/projectiles/orb_green_dragon.lua` periodically.

## Entity Structure

The entity is composed of a main `Entity` tag containing various components. A nested `Entity` is present, which seems to function as a turret, inheriting the transform of a specific sprite (`parent_sprite_id="10"`) and firing projectiles.

## Tags

The dragon entity has the following tags: `mortal`, `hittable`, `teleportable_NOT`, `enemy`. The `teleportable_NOT` tag is significant, indicating it cannot be teleported.