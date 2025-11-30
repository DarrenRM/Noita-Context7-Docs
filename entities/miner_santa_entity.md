---
title: Miner Santa Entity
category: entities
---

# Miner Santa Entity

This document details the `miner_santa.xml` entity, a hostile creature in Noita.

## Core Attributes

The Miner Santa is a basic enemy with several key behavioral and physical attributes defined by its components.

### Base Enemy Configuration

The entity inherits fundamental properties from `base_enemy_basic.xml`.

### Animal AI Component

This component governs the creature's behavior, including combat, detection, and survival.

| Attribute                       | Value                               | Description                                                                 |
| :------------------------------ | :---------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault`                        | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability` | `40`                                | Percentage chance to flee when damaged.                                     |
| `attack_melee_damage_min`       | `0.4`                               | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | `0.7`                               | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`    | `300`                               | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`    | `300`                               | Vertical range for detecting other creatures.                               |
| `food_material`                 | `meat`                              | The material type this creature consumes for food.                          |
| `needs_food`                    | `1`                                 | Whether the creature requires food to survive.                              |
| `sense_creatures`               | `1`                                 | Whether the creature can detect other creatures.                            |
| `attack_ranged_enabled`         | `1`                                 | Enables ranged attacks.                                                     |
| `attack_melee_enabled`          | `1`                                 | Enables melee attacks.                                                      |
| `attack_only_if_attacked`       | `1`                                 | The creature will only attack if it has been attacked first.                |
| `can_fly`                       | `0`                                 | The creature cannot fly.                                                    |
| `attack_ranged_action_frame`    | `4`                                 | The animation frame at which a ranged attack is initiated.                  |
| `attack_ranged_entity_file`     | `data/entities/projectiles/present.xml` | The projectile entity file used for ranged attacks (presents).              |
| `attack_ranged_frames_between`  | `400`                               | The number of animation frames between ranged attacks.                      |

### Damage Model Component

Defines the creature's health and how it reacts to damage.

| Attribute                     | Value                               | Description                                                                 |
| :---------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                          | `4`                                 | The creature's hit points.                                                  |
| `materials_create_messages`   | `1`                                 | Whether damage to specific materials generates messages.                    |
| `ragdoll_filenames_file`      | `data/ragdolls/miner_santa/filenames.txt` | Specifies the files used for the creature's ragdoll effect upon death.      |
| `fire_probability_of_ignition`| `5`                                 | The percentage chance the creature will ignite when hit by fire.            |

### Sprite Component

Determines the visual appearance of the Miner Santa.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/miner_santa.xml`  | The XML file defining the creature's sprites. |
| `offset_x`  | `0`                                 | Horizontal offset for the sprite.         |
| `offset_y`  | `0`                                 | Vertical offset for the sprite.           |

### Path Finding Component

Controls the creature's movement capabilities.

| Attribute                   | Value | Description                                     |
| :-------------------------- | :---- | :---------------------------------------------- |
| `can_jump`                  | `1`   | The creature can jump.                          |
| `can_fly`                   | `0`   | The creature cannot fly.                        |
| `jump_speed`                | `100` | The speed at which the creature jumps.          |
| `initial_jump_lob`          | `1`   | Controls the arc of the jump.                   |
| `initial_jump_max_distance_x`| `60`  | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y`| `60`  | Maximum vertical distance of a jump.            |

### Path Finding Grid Marker Component

Used for pathfinding grid calculations.

| Attribute      | Value | Description                                     |
| :------------- | :---- | :---------------------------------------------- |
| `marker_work_flag`| `16`  | A flag used by the pathfinding system.          |

### Genome Data Component

Defines genetic traits and ecological role.

| Attribute         | Value | Description                                     |
| :---------------- | :---- | :---------------------------------------------- |
| `herd_id`         | `orcs`| The identifier for the creature's herd or group. |
| `food_chain_rank` | `9`   | Its position in the food chain (higher is higher). |
| `is_predator`     | `1`   | Indicates if the creature is a predator.        |

### Character Platforming Component

Governs ground-based movement.

| Attribute     | Value | Description                                     |
| :------------ | :---- | :---------------------------------------------- |
| `jump_velocity_y`| `-12` | The vertical velocity applied when jumping.     |
| `run_velocity`| `12`  | The horizontal movement speed.                  |

### Camera Bound Component

Manages how the camera interacts with the creature.

| Attribute   | Value   | Description                                     |
| :---------- | :------ | :---------------------------------------------- |
| `max_count` | `30`    | Maximum number of this entity the camera tracks. |
| `distance`  | `160000`| The distance at which the entity affects the camera. |

### Hitbox Component

Defines the collision area for interactions.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `aabb_max_x`| `5`   | Maximum X-coordinate of the bounding box.       |
| `aabb_max_y`| `3`   | Maximum Y-coordinate of the bounding box.       |
| `aabb_min_x`| `-5`  | Minimum X-coordinate of the bounding box.       |
| `aabb_min_y`| `-12` | Minimum Y-coordinate of the bounding box.       |

### Character Data Component

Provides general character physics and collision data.

| Attribute         | Value | Description                                     |
| :---------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x`| `-2.0`| Minimum X-coordinate for character collision.   |
| `collision_aabb_max_x`| `2.0` | Maximum X-coordinate for character collision.   |
| `collision_aabb_min_y`| `-7.5`| Minimum Y-coordinate for character collision.   |
| `collision_aabb_max_y`| `3`   | Maximum Y-coordinate for character collision.   |
| `mass`            | `1.3` | The mass of the character.                      |

## Additional Components

### Light Component

Adds a light source to the entity.

| Attribute | Value | Description                                     |
| :-------- | :---- | :---------------------------------------------- |
| `radius`  | `50`  | The radius of the light.                        |
| `fade_out_time`| `1.5` | The time it takes for the light to fade out.    |

### Item Pick Upper Component

Allows the entity to pick up items.

| Attribute   | Value | Description                                     |
| :---------- | :---- | :---------------------------------------------- |
| `is_in_npc` | `1`   | Indicates if this is part of an NPC interaction. |

### Game Effect Component

Applies a persistent game effect to the entity.

| Attribute | Value     | Description                                     |
| :-------- | :-------- | :---------------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE` | The game effect applied (Radioactive Allergy). |
| `frames`  | `-1`      | The duration of the effect (-1 means infinite). |

### Hotspot Component

Defines interaction points on the entity.

| Attribute          | Value | Description                                     |
| :----------------- | :---- | :---------------------------------------------- |
| `_tags`            | `hand_hotspot,hand` | Tags associated with this hotspot.              |
| `sprite_hotspot_name`| `hand`| The name of the sprite hotspot.                 |
| `offset.x`         | `0`   | Horizontal offset of the hotspot.               |
| `offset.y`         | `0`   | Vertical offset of the hotspot.                 |