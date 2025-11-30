---
title: Zombie Entity Configuration
category: entities
---

# Zombie Entity Configuration

This document details the configuration of the Zombie entity in Noita, focusing on key attributes relevant for AI-assisted modding.

## Entity Definition

The core definition of the zombie entity.

```xml
<Entity tags="zombie" name="$animal_zombie">
  <!-- ... other components ... -->
</Entity>
```

## Base Enemy Configuration

The zombie inherits fundamental behaviors and properties from `base_enemy_basic.xml`.

### AnimalAIComponent

This component governs the zombie's artificial intelligence and behavior.

| Attribute                       | Description                                                                 |
| :------------------------------ | :-------------------------------------------------------------------------- |
| `_enabled`                      | Enables or disables the AI component.                                       |
| `preferred_job`                 | The primary job the AI will attempt to perform (e.g., `JobDefault`).        |
| `escape_if_damaged_probability` | Percentage chance to flee when taking damage.                               |
| `attack_melee_damage_min`       | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | Maximum damage dealt by melee attacks.                                      |
| `attack_dash_enabled`           | Enables a dashing attack.                                                   |
| `creature_detection_range_x`    | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`    | Vertical range for detecting other creatures.                               |
| `food_material`                 | The material the creature considers food.                                   |
| `needs_food`                    | Whether the creature requires food to survive.                              |
| `sense_creatures`               | Whether the creature can detect other creatures.                            |
| `attack_ranged_enabled`         | Enables ranged attacks (set to `0` for zombies).                            |
| `can_fly`                       | Whether the creature can fly (set to `0` for zombies).                      |
| `defecates_and_pees`            | Whether the creature has bodily functions.                                  |

### DamageModelComponent

Defines the zombie's health, damage resistances, and how it reacts to damage.

| Attribute                  | Description                                                                 |
| :------------------------- | :-------------------------------------------------------------------------- |
| `hp`                       | Hit points of the zombie.                                                   |
| `materials_create_messages`| Whether damage events create messages.                                      |
| `ragdoll_material`         | The material used for the zombie's ragdoll.                                 |
| `blood_material`           | The material used for blood splatters.                                      |
| `blood_spray_material`     | The material used for blood spray effects.                                  |
| `ragdoll_filenames_file`   | Path to the file defining ragdoll bone structures.                          |
| `blood_sprite_directional` | Path to directional blood splatter particle effects.                        |
| `blood_sprite_large`       | Path to large blood splatter particle effects.                              |
| `physics_objects_damage`   | Whether physics objects can damage the zombie.                              |
| `blood_spray_create_some_cosmetic` | Whether to create cosmetic blood spray effects.                         |

#### Damage Multipliers

Specific resistances or weaknesses to damage types.

| Damage Type | Multiplier | Description                               |
| :---------- | :--------- | :---------------------------------------- |
| `holy`      | `1.2`      | Takes 20% more damage from holy sources.  |

### SpriteComponent (Main)

Defines the primary visual appearance of the zombie.

| Attribute    | Description                                     |
| :----------- | :---------------------------------------------- |
| `image_file` | Path to the sprite sheet or animation definition. |
| `offset_x`   | Horizontal offset for the sprite.               |
| `offset_y`   | Vertical offset for the sprite.                 |

### PathFindingComponent

Controls how the zombie navigates the game world.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `distance_to_reach_node_x`| Horizontal distance considered "reached" for pathfinding nodes.             |
| `distance_to_reach_node_y`| Vertical distance considered "reached" for pathfinding nodes.               |
| `can_swim_on_surface`     | Whether the zombie can swim on the surface of liquids.                      |
| `can_dive`                | Whether the zombie can dive into liquids.                                   |
| `frames_to_get_stuck`     | Number of frames before the AI considers itself stuck.                      |
| `can_jump`                | Whether the zombie can jump.                                                |

### GenomeDataComponent

Defines the zombie's place in the game's ecosystem and genetics.

| Attribute         | Description                                     |
| :---------------- | :---------------------------------------------- |
| `herd_id`         | Identifier for the zombie's species or group.   |
| `food_chain_rank` | Position in the food chain (higher is higher).  |
| `is_predator`     | Whether the zombie is a predator.               |

### CharacterDataComponent

Basic physical properties of the character.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `buoyancy_check_offset_y` | Vertical offset for buoyancy checks.            |
| `collision_aabb_min_x` | Minimum X-coordinate of the collision box.      |
| `collision_aabb_max_x` | Maximum X-coordinate of the collision box.      |
| `collision_aabb_min_y` | Minimum Y-coordinate of the collision box.      |
| `collision_aabb_max_y` | Maximum Y-coordinate of the collision box.      |
| `mass`              | The mass of the zombie.                         |

### CharacterPlatformingComponent

Governs movement and platforming abilities.

| Attribute                               | Description                                                                 |
| :-------------------------------------- | :-------------------------------------------------------------------------- |
| `pixel_gravity`                         | The strength of gravity applied to the zombie in pixels per frame.          |
| `jump_velocity_y`                       | The vertical velocity applied when jumping.                                 |
| `run_velocity`                          | The base running speed of the zombie.                                       |
| `run_animation_velocity_switching_enabled` | Enables dynamic switching of run animations based on velocity.              |
| `run_animation_velocity_switching_threshold` | The velocity threshold for switching run animations.                        |

### HitboxComponent

Defines the interactive hit area of the zombie.

| Attribute | Description                                     |
| :-------- | :---------------------------------------------- |
| `aabb_min_x` | Minimum X-coordinate of the hitbox.             |
| `aabb_max_x` | Maximum X-coordinate of the hitbox.             |
| `aabb_min_y` | Minimum Y-coordinate of the hitbox.             |
| `aabb_max_y` | Maximum Y-coordinate of the hitbox.             |
| `is_enemy` | Whether this hitbox belongs to an enemy.         |
| `is_item`  | Whether this hitbox belongs to an item.          |
| `is_player`| Whether this hitbox belongs to the player.       |

### CameraBoundComponent

Controls how the camera behaves relative to the zombie.

| Attribute   | Description                                     |
| :---------- | :---------------------------------------------- |
| `max_count` | Maximum number of entities this component can affect. |
| `distance`  | The distance at which the camera is affected.   |

## Audio Component

Defines the sound effects associated with the zombie.

```xml
<AudioComponent
	file="data/audio/Desktop/animals.bank"
	event_root="animals/zombie" >
</AudioComponent>
```

*   `file`: Path to the audio bank.
*   `event_root`: The base event name for zombie sounds.

## Sprite Component (Emissive)

Defines the emissive visual effects for the zombie, often used for glowing or special states.

```xml
<SpriteComponent
    _tags="character"
    alpha="1"
    image_file="data/enemies_gfx/zombie_emissive.xml"
    emissive="1"
    additive="1"
    rect_animation="walk" >
</SpriteComponent>
```

*   `_tags`: Tags applied to this sprite component.
*   `alpha`: Transparency of the sprite.
*   `image_file`: Path to the emissive sprite definition.
*   `emissive`: Enables emissive rendering.
*   `additive`: Uses additive blending for the emissive effect.
*   `rect_animation`: Specifies the default rectangle animation to use (e.g., "walk").