---
title: Worm End Entity
category: entities
---

# Worm End Entity

This document describes the `worm_end.xml` entity, representing the head of a worm enemy in Noita. It details its core components and key attributes relevant for AI-assisted modding.

## Entity Overview

The `worm_end` entity is a hostile creature with the following primary tags: `mortal`, `hittable`, `enemy`, `worm`. It is designed to be a segment of a larger worm, with specific AI and physical properties.

## Key Components and Attributes

### WormComponent

This component governs the physical behavior and movement mechanics of the worm.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `acceleration`      | The rate at which the worm accelerates.                                  |
| `gravity`           | The gravitational pull affecting the worm's body segments.               |
| `tail_gravity`      | The gravitational pull specifically affecting the tail segments.         |
| `part_distance`     | The desired distance between connected worm segments.                    |
| `ground_check_offset` | Offset for checking if the worm is on the ground.                        |
| `hitbox_radius`     | The radius of the worm's hitbox for collisions and damage.               |
| `bite_damage`       | The amount of damage dealt by the worm's bite.                           |
| `target_kill_radius`| Radius within which the worm can instantly kill its target.              |
| `ragdoll_filename`  | Specifies the ragdoll file used when the worm dies.                    |

### WormAIComponent

This component defines the artificial intelligence and target acquisition behavior of the worm.

| Attribute                      | Description                                                              |
| :----------------------------- | :----------------------------------------------------------------------- |
| `speed`                        | The base movement speed of the worm.                                     |
| `speed_hunt`                   | The increased speed when actively hunting a target.                      |
| `direction_adjust_speed`       | How quickly the worm adjusts its direction.                              |
| `direction_adjust_speed_hunt`  | Faster direction adjustment when hunting.                                |
| `hunt_box_radius`              | The radius within which the worm will actively hunt for targets.         |
| `random_target_box_radius`     | The radius for seeking random targets when not actively hunting.         |
| `new_hunt_target_check_every`  | Frequency (in frames) of checking for new hunt targets.                  |
| `give_up_area_radius`          | Radius within which the worm will give up pursuing a target.             |
| `give_up_time_frames`          | Duration (in frames) the worm will pursue before giving up.              |

### DamageModelComponent

This component handles the health, damage resistances, and damage taken by the worm.

| Attribute                  | Description                                                              |
| :------------------------- | :----------------------------------------------------------------------- |
| `hp`                       | The hit points of the worm.                                              |
| `fire_damage_amount`       | The amount of damage taken from fire.                                    |
| `fire_probability_of_ignition` | Probability of igniting from fire damage.                                |
| `materials_damage`         | Whether the worm takes damage from specific materials.                   |
| `materials_that_damage`    | The specific materials that inflict damage.                              |
| `blood_material`           | The material of the blood/gore produced.                                 |
| `blood_sprite_directional` | Sprite for directional blood splatters.                                  |
| `blood_sprite_large`       | Sprite for larger blood splatters.                                       |

#### `damage_multipliers`

This nested element defines multipliers for damage taken from different sources.

| Attribute   | Multiplier | Description                               |
| :---------- | :--------- | :---------------------------------------- |
| `drill`     | `0.4`      | Damage multiplier from drills.            |
| `projectile`| `0.4`      | Damage multiplier from projectiles.       |
| `holy`      | `1.2`      | Damage multiplier from holy sources.      |

### SpriteComponent

Multiple `SpriteComponent` elements define the visual appearance of the worm's segments.

| Attribute       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `image_file`    | The path to the sprite image file.                                       |
| `rect_animation`| The animation state to use for the sprite.                               |
| `offset_x`      | Horizontal offset for the sprite.                                        |
| `offset_y`      | Vertical offset for the sprite.                                          |
| `z_index`       | Determines the rendering order of the sprite.                            |

*   The first `SpriteComponent` uses `endworm_head.xml`.
*   Subsequent `SpriteComponent` elements use `endworm_middle.xml` for body segments.
*   The last `SpriteComponent` uses `endworm_tail.xml`.

### GenomeDataComponent

This component provides genetic information for the worm, influencing its behavior within the game's ecosystem.

| Attribute         | Description                               |
| :---------------- | :---------------------------------------- |
| `herd_id`         | Identifier for the worm's herd.           |
| `food_chain_rank` | Position in the food chain.               |
| `is_predator`     | Indicates if the creature is a predator.  |

### AudioComponent & AudioLoopComponent

These components manage the sound effects associated with the worm, including movement loops and general animal sounds.

*   `AudioComponent` with `event_root="animals"` for general animal sounds.
*   `AudioComponent` with `event_root="animals/worm"` for worm-specific sounds.
*   `AudioLoopComponent` for a continuous movement sound effect.

## Modding Considerations

*   **AI Behavior:** Adjusting parameters in `WormAIComponent` can significantly alter how the worm hunts, pursues, and gives up on targets.
*   **Combat:** Modifying `bite_damage` in `WormComponent` or `hp` and `damage_multipliers` in `DamageModelComponent` will change its combat effectiveness and survivability.
*   **Visuals:** The `SpriteComponent` elements can be swapped with custom graphics for different worm appearances. The number of `endworm_middle.xml` sprites determines the worm's length.
*   **Physics:** `acceleration`, `gravity`, and `part_distance` in `WormComponent` can be tweaked to alter the worm's movement feel and segment linkage.