---
title: Wizard Twitchy Entity
category: entities
---

# Wizard Twitchy Entity

This document details the `wizard_twitchy.xml` entity, a flying, ranged-attacking creature in Noita.

## Core Attributes

The `wizard_twitchy` entity is primarily defined by its `Base` entity, inheriting many properties from `base_enemy_basic.xml`. Key components and their significant attributes are listed below.

### AnimalAIComponent

Controls the creature's behavior, senses, and attacks.

| Attribute                  | Value                                     | Description                                                                 |
| :------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `creature_detection_range_x` | `400`                                     | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y` | `400`                                     | Vertical range for detecting other creatures.                               |
| `food_material`            | `blood`                                   | The material this creature considers food.                                  |
| `needs_food`               | `0`                                       | Whether the creature requires food to survive.                              |
| `sense_creatures`          | `1`                                       | Enables creature sensing.                                                   |
| `attack_ranged_enabled`    | `1`                                       | Enables ranged attacks.                                                     |
| `can_fly`                  | `1`                                       | Allows the creature to fly.                                                 |
| `attack_ranged_entity_file`| `data/entities/projectiles/orb_twitchy.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_frames_between`| `70`                                      | Frames between consecutive ranged attacks.                                  |
| `attack_ranged_max_distance`| `300`                                     | Maximum distance for ranged attacks.                                        |

### DamageModelComponent

Defines the creature's health and damage resistance.

| Attribute                  | Value                               | Description                                     |
| :------------------------- | :---------------------------------- | :---------------------------------------------- |
| `hp`                       | `5`                                 | Hit points of the creature.                     |
| `ragdoll_material`         | `meat_fast`                         | Material used for the ragdoll upon death.       |
| `critical_damage_resistance`| `0.4`                               | Resistance to critical damage.                  |

### SpriteComponent

Handles the visual representation of the creature.

| Attribute    | Value                               | Description                                     |
| :----------- | :---------------------------------- | :---------------------------------------------- |
| `image_file` | `data/enemies_gfx/wizard_twitchy.xml` | Path to the sprite's image definition file.     |

### CharacterPlatformingComponent

Governs movement and physics related to character movement.

| Attribute      | Value | Description                                     |
| :------------- | :---- | :---------------------------------------------- |
| `jump_velocity_y`| `-90` | Vertical velocity applied when jumping.         |
| `run_velocity` | `36`  | Horizontal movement speed.                      |
| `fly_velocity_x` | `56`  | Horizontal speed when flying.                   |
| `accel_x`      | `0.09`| Horizontal acceleration.                        |

### HitboxComponent

Defines the physical collision boundaries of the entity.

| Attribute     | Value | Description                                     |
| :------------ | :---- | :---------------------------------------------- |
| `aabb_min_x`  | `-4.5`| Minimum X-coordinate of the bounding box.       |
| `aabb_max_x`  | `4.5` | Maximum X-coordinate of the bounding box.       |
| `aabb_min_y`  | `-10` | Minimum Y-coordinate of the bounding box.       |
| `aabb_max_y`  | `3`   | Maximum Y-coordinate of the bounding box.       |

### CharacterDataComponent

Provides additional character-specific data, including collision boxes.

| Attribute             | Value | Description                                     |
| :-------------------- | :---- | :---------------------------------------------- |
| `collision_aabb_min_x`| `-3.0`| Minimum X-coordinate for character collision.   |
| `collision_aabb_max_x`| `3.0` | Maximum X-coordinate for character collision.   |
| `collision_aabb_min_y`| `-7`  | Minimum Y-coordinate for character collision.   |
| `collision_aabb_max_y`| `3`   | Maximum Y-coordinate for character collision.   |

## Special Components

### SpriteParticleEmitterComponent

Responsible for emitting particles, in this case, smoke effects.

| Attribute             | Value                               | Description                                     |
| :-------------------- | :---------------------------------- | :---------------------------------------------- |
| `sprite_file`         | `data/particles/smoke_02.xml`       | The particle effect to emit.                    |
| `lifetime`            | `2`                                 | Duration of each particle in seconds.           |
| `gravity.y`           | `30`                                | Gravity applied to particles.                   |
| `emission_interval_min_frames` | `5`                                 | Minimum frames between particle emissions.      |
| `emission_interval_max_frames` | `10`                                | Maximum frames between particle emissions.      |
| `count_min`           | `1`                                 | Minimum particles emitted per emission.         |
| `count_max`           | `1`                                 | Maximum particles emitted per emission.         |
| `randomize_rotation.min`| `-3.1415`                           | Minimum random rotation for particles.          |
| `randomize_rotation.max`| `3.1415`                            | Maximum random rotation for particles.          |
| `randomize_velocity.min_x`| `-5`                                | Minimum random X velocity for particles.        |
| `randomize_velocity.max_x`| `5`                                 | Maximum random X velocity for particles.        |
| `randomize_position.min_x`| `-10`                               | Minimum random X position offset for particles. |
| `randomize_position.max_x`| `10`                                | Maximum random X position offset for particles. |

### AudioLoopComponent

Plays a looping sound effect for the creature's movement.

| Attribute   | Value                                | Description                                     |
| :---------- | :----------------------------------- | :---------------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`    | The audio bank containing the sound event.      |
| `event_name`| `animals/wizard/movement_loop`       | The specific sound event to play.               |
| `auto_play` | `1`                                  | Starts playing automatically when spawned.      |

### MagicConvertMaterialComponent

Allows the creature to convert materials.

| Attribute       | Value     | Description                                     |
| :-------------- | :-------- | :---------------------------------------------- |
| `from_material` | `rock_box2d_hard` | The material to convert from.                   |
| `to_material`   | `air`     | The material to convert to.                     |
| `radius`        | `15`      | The radius of the conversion effect.            |
| `loop`          | `1`       | Whether the conversion effect loops.            |

### Entity "cape"

This nested entity defines a cape attached to the wizard, utilizing Verlet physics for cloth simulation.

#### VerletPhysicsComponent (within cape)

| Attribute      | Value     | Description                                     |
| :------------- | :-------- | :---------------------------------------------- |
| `cloth_color`  | `0xFF284335`| The primary color of the cloth.                 |
| `cloth_color_edge`| `0xFFb7d3ad`| The edge color of the cloth.                  |

### SpriteComponent (Emissive)

This component defines an additional, emissive sprite for the wizard, likely for visual effects like glowing.

| Attribute    | Value                                     | Description                                     |
| :----------- | :---------------------------------------- | :---------------------------------------------- |
| `image_file` | `data/enemies_gfx/wizard_twitchy_emissive.xml` | Path to the emissive sprite's image definition. |
| `emissive`   | `1`                                       | Enables emissive properties.                    |
| `additive`   | `1`                                       | Uses additive blending for the emissive effect. |
| `rect_animation`| `walk`                                    | Specifies the active rectangle animation.       |