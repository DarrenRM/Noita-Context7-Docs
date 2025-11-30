---
title: Shotgunner Hell Entity
category: entities
---

# Shotgunner Hell Entity

This document details the `shotgunner_hell.xml` entity, a hostile creature in Noita. It focuses on key attributes relevant to AI modding, such as its combat behavior, movement, and damage properties.

## Core Attributes

The `shotgunner_hell` entity inherits from `base_enemy_basic.xml` and possesses several defining components.

### AnimalAIComponent

This component governs the creature's artificial intelligence and combat capabilities.

| Attribute                       | Value                                     | Description                                                                 |
| :------------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`                 | `JobDefault`                              | Default AI behavior.                                                        |
| `escape_if_damaged_probability` | `30`                                      | Probability (in percent) of escaping when damaged.                          |
| `attack_melee_damage_min`       | `1.4`                                     | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`       | `1.7`                                     | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`    | `400`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`    | `200`                                     | Vertical range for detecting creatures.                                     |
| `creature_detection_angular_range_deg` | `60`                                      | Angular range (in degrees) for detecting creatures.                         |
| `attack_melee_max_distance`     | `12`                                      | Maximum distance for melee attacks.                                         |
| `food_material`                 | `meat`                                    | Material the creature consumes for food.                                    |
| `needs_food`                    | `1`                                       | Whether the creature requires food.                                         |
| `sense_creatures`               | `1`                                       | Whether the creature can sense other creatures.                             |
| `attack_ranged_enabled`         | `1`                                       | Enables ranged attacks.                                                     |
| `attack_melee_enabled`          | `1`                                       | Enables melee attacks.                                                      |
| `attack_ranged_entity_file`     | `data/entities/projectiles/buckshot.xml`  | The projectile entity file used for ranged attacks.                         |
| `attack_ranged_entity_count_min`| `12`                                      | Minimum number of projectiles fired per ranged attack.                      |
| `attack_ranged_entity_count_max`| `16`                                      | Maximum number of projectiles fired per ranged attack.                      |
| `attack_ranged_frames_between`  | `70`                                      | Frames between ranged attacks.                                              |
| `attack_ranged_offset_y`        | `-7`                                      | Vertical offset for ranged attack origin.                                   |

### DamageModelComponent

Defines the creature's health and how it takes damage.

| Attribute                   | Value                               | Description                                                                 |
| :-------------------------- | :---------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                        | `2.9`                               | Hit points of the creature.                                                 |
| `blood_spray_material`      | `liquid_fire`                       | Material of the blood spray effect.                                         |
| `blood_material`            | `liquid_fire`                       | Material of the blood.                                                      |
| `blood_spray_create_some_cosmetic` | `1`                                 | Whether to create cosmetic blood particles.                                 |
| `blood_multiplier`          | `1.2`                               | Multiplier for blood effects.                                               |

#### Damage Multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `projectile`| `0.6`      |
| `explosion` | `0.6`      |
| `slice`     | `1`        |
| `ice`       | `0`        |
| `fire`      | `0`        |
| `holy`      | `2.0`      |

### SpriteComponent

Determines the visual representation of the creature.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/shotgunner_hell.xml`| Path to the sprite's XML definition.      |
| `offset_x`  | `8`                                 | Horizontal offset of the sprite.          |
| `offset_y`  | `13`                                | Vertical offset of the sprite.            |

### PathFindingComponent

Controls the creature's movement and navigation capabilities.

| Attribute                   | Value | Description                                     |
| :-------------------------- | :---- | :---------------------------------------------- |
| `can_jump`                  | `1`   | Whether the creature can jump.                  |
| `can_fly`                   | `0`   | Whether the creature can fly.                   |
| `jump_speed`                | `80`  | Speed of jumping.                               |
| `initial_jump_max_distance_x`| `60`  | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y`| `60`  | Maximum vertical distance of a jump.            |
| `can_swim_on_surface`       | `1`   | Whether the creature can swim on the surface.   |
| `can_dive`                  | `1`   | Whether the creature can dive.                  |

### CharacterPlatformingComponent

Defines specific platforming movement parameters.

| Attribute       | Value | Description                               |
| :-------------- | :---- | :---------------------------------------- |
| `jump_velocity_y`| `-14` | Vertical velocity when jumping.           |
| `run_velocity`  | `25`  | Horizontal movement speed.                |

### CharacterDataComponent

Basic character properties like collision and mass.

| Attribute           | Value | Description                               |
| :------------------ | :---- | :---------------------------------------- |
| `collision_aabb_min_x`| `-2.0`| Minimum X-axis for collision bounding box.|
| `collision_aabb_max_x`| `2.0` | Maximum X-axis for collision bounding box.|
| `collision_aabb_min_y`| `-8`  | Minimum Y-axis for collision bounding box.|
| `collision_aabb_max_y`| `3`   | Maximum Y-axis for collision bounding box.|
| `mass`              | `1.3` | Mass of the character.                    |

## Other Notable Components

### LightComponent

Adds a light source to the entity.

| Attribute   | Value | Description                               |
| :---------- | :---- | :---------------------------------------- |
| `radius`    | `50`  | The radius of the light.                  |
| `fade_out_time`| `1.5` | Time it takes for the light to fade out.|

### AudioComponent

Manages the entity's sound effects.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`   | Path to the audio bank.                   |
| `event_root`| `animals/shotgunner`                | Root event name for animal sounds.        |

### GameEffectComponent

Applies a persistent game effect to the entity.

| Attribute | Value              | Description                               |
| :-------- | :----------------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE`| The game effect applied.                  |
| `frames`  | `-1`               | Duration of the effect (-1 for infinite). |

### ParticleEmitterComponent

Responsible for emitting particles, likely for visual feedback during attacks or damage.

| Attribute                 | Value | Description                                     |
| :------------------------ | :---- | :---------------------------------------------- |
| `emitted_material_name`   | `blood`| The material of the emitted particles.          |
| `x_pos_offset_min`        | `-4`  | Minimum X-axis offset for particle emission.    |
| `x_pos_offset_max`        | `4`   | Maximum X-axis offset for particle emission.    |
| `y_pos_offset_min`        | `-4`  | Minimum Y-axis offset for particle emission.    |
| `y_pos_offset_max`        | `4`   | Maximum Y-axis offset for particle emission.    |
| `x_vel_min`               | `-8`  | Minimum X-axis velocity for emitted particles.  |
| `x_vel_max`               | `8`   | Maximum X-axis velocity for emitted particles.  |
| `gravity.y`               | `1.0` | Gravity applied to emitted particles.           |
| `y_vel_min`               | `-8`  | Minimum Y-axis velocity for emitted particles.  |
| `y_vel_max`               | `8`   | Maximum Y-axis velocity for emitted particles.  |
| `count_min`               | `1`   | Minimum number of particles emitted per burst.  |
| `count_max`               | `2`   | Maximum number of particles emitted per burst.  |
| `lifetime_min`            | `0.1` | Minimum lifetime of emitted particles.          |
| `lifetime_max`            | `0.6` | Maximum lifetime of emitted particles.          |
| `create_real_particles`   | `0`   | Whether to create actual game particles.        |
| `emit_cosmetic_particles` | `1`   | Whether to emit cosmetic particles.             |
| `emission_interval_min_frames`| `3`   | Minimum frames between particle emissions.      |
| `emission_interval_max_frames`| `5`   | Maximum frames between particle emissions.      |
| `is_emitting`             | `1`   | Whether particle emission is active.            |