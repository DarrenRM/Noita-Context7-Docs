---
title: Base Robot Boss Limbs Entity
category: entities
---

# Base Robot Boss Limbs Entity

This XML defines the base properties for robot boss limbs in Noita. It inherits from `base_humanoid.xml` and customizes AI, damage, visuals, and movement.

## Key Components

### AnimalAIComponent
Controls the AI behavior of the entity.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `creature_detection_range_x` | Horizontal range for detecting creatures.                                |
| `creature_detection_range_y` | Vertical range for detecting creatures.                                  |
| `attack_melee_damage_min` | Minimum damage for melee attacks.                                        |
| `attack_melee_damage_max` | Maximum damage for melee attacks.                                        |
| `food_material`           | Material the creature consumes for sustenance.                           |
| `needs_food`              | Whether the creature requires food.                                      |
| `sense_creatures`         | Whether the creature can sense other creatures.                          |
| `aggressiveness_min`      | Minimum aggressiveness level.                                            |
| `aggressiveness_max`      | Maximum aggressiveness level.                                            |

### DamageModelComponent
Defines the entity's health, damage resistances, and how it reacts to damage.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `hp`                      | Hit points of the entity.                                                |
| `ragdoll_material`        | Material used for the ragdoll when the entity dies.                      |
| `blood_material`          | Material that acts as blood when the entity is damaged.                  |
| `blood_spray_material`    | Material for blood spray effects.                                        |
| `materials_that_damage`   | List of materials that inflict damage to this entity.                    |
| `materials_how_much_damage` | Corresponding damage values for `materials_that_damage`.                 |
| `air_needed`              | Whether the entity requires air to survive.                              |

#### damage_multipliers
Specific multipliers for different damage types.

| Damage Type   | Multiplier |
| :------------ | :--------- |
| `fire`        | `0.0`      |
| `drill`       | `0.1`      |
| `slice`       | `0.1`      |
| `melee`       | `0.3`      |
| `projectile`  | `0.5`      |
| `radioactive` | `0.0`      |
| `explosion`   | `1.0`      |
| `electricity` | `2.0`      |

### SpriteComponent
Determines the visual appearance of the entity.

| Attribute     | Description                                  |
| :------------ | :------------------------------------------- |
| `image_file`  | Path to the sprite's image definition file.  |
| `z_index`     | Rendering order relative to other sprites.   |

### PathFindingComponent
Configures how the entity navigates the game world.

| Attribute               | Description                                      |
| :---------------------- | :----------------------------------------------- |
| `distance_to_reach_node_x` | Horizontal distance to consider a node reached.  |
| `distance_to_reach_node_y` | Vertical distance to consider a node reached.    |
| `frames_to_get_stuck`   | Frames before entity is considered stuck.        |
| `can_jump`              | Whether the entity can jump.                     |

### CharacterPlatformingComponent
Handles the entity's movement physics and animations.

| Attribute                               | Description                                      |
| :-------------------------------------- | :----------------------------------------------- |
| `accel_x`                               | Horizontal acceleration.                         |
| `pixel_gravity`                         | Gravity applied to the entity in pixels/frame.   |
| `jump_velocity_y`                       | Vertical velocity applied when jumping.          |
| `run_velocity`                          | Base running speed.                              |
| `run_animation_velocity_switching_enabled` | Enables switching run animations based on speed. |
| `run_animation_velocity_switching_threshold` | Speed threshold for animation switching.         |

### HitboxComponent
Defines the collision boundaries for the entity.

| Attribute      | Description                                      |
| :------------- | :----------------------------------------------- |
| `aabb_min_x`   | Minimum X-coordinate of the bounding box.        |
| `aabb_max_x`   | Maximum X-coordinate of the bounding box.        |
| `aabb_min_y`   | Minimum Y-coordinate of the bounding box.        |
| `aabb_max_y`   | Maximum Y-coordinate of the bounding box.        |

### CharacterDataComponent
General character-specific data.

| Attribute                 | Description                                      |
| :------------------------ | :----------------------------------------------- |
| `climb_over_y`            | Vertical distance the character can climb over.  |
| `collision_aabb_min_x`    | Minimum X for collision detection.               |
| `collision_aabb_max_x`    | Maximum X for collision detection.               |
| `collision_aabb_min_y`    | Minimum Y for collision detection.               |
| `collision_aabb_max_y`    | Maximum Y for collision detection.               |
| `buoyancy_check_offset_y` | Offset for buoyancy checks.                      |

### AudioComponent
Manages the sound effects associated with the entity.

| Attribute     | Description                                      |
| :------------ | :----------------------------------------------- |
| `file`        | Path to the audio bank file.                     |
| `event_root`  | Root event name for sounds.                      |
| `set_latest_event_position` | Whether to set the sound's position to the latest event. |