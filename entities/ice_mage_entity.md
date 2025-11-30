---
title: Ice Mage Entity
category: entities
---

# Ice Mage Entity

This document details the configuration of the Ice Mage entity in Noita, focusing on its AI, combat capabilities, and visual/audio properties.

## Core Attributes

The Ice Mage is a flying enemy with ranged ice attacks and moderate health.

### `AnimalAIComponent`

This component governs the creature's behavior and combat logic.

| Attribute                     | Value                                     | Description                                                                 |
| :---------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `preferred_job`               | `JobDefault`                              | Default job assigned to the creature.                                       |
| `attack_melee_damage_min`     | `0.4`                                     | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`     | `0.7`                                     | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`  | `300`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `300`                                     | Vertical range for detecting creatures.                                     |
| `food_material`               | `blood`                                   | Material the creature consumes for sustenance.                              |
| `needs_food`                  | `0`                                       | Whether the creature requires food to survive (0 = no).                     |
| `sense_creatures`             | `1`                                       | Whether the creature can sense other creatures.                             |
| `attack_ranged_enabled`       | `1`                                       | Whether ranged attacks are enabled.                                         |
| `can_fly`                     | `1`                                       | Whether the creature can fly.                                               |
| `attack_ranged_entity_file`   | `data/entities/projectiles/iceball.xml`   | The entity file for the projectile used in ranged attacks.                  |
| `attack_ranged_action_frame`  | `3`                                       | The animation frame at which the ranged attack is initiated.                |
| `attack_ranged_frames_between`| `140`                                     | The number of animation frames between ranged attacks.                      |

### `DamageModelComponent`

Defines the entity's health, resistances, and how it takes damage.

| Attribute                     | Value                                     | Description                                                                 |
| :---------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                          | `5`                                       | Hit points of the entity.                                                   |
| `ragdoll_material`            | `ice`                                     | The material used for the ragdoll when the entity dies.                     |
| `fire_probability_of_ignition`| `0`                                       | Probability of igniting from fire damage.                                   |
| `blood_material`              | `snow`                                    | The material that acts as blood when the entity is damaged.                 |
| `materials_that_damage`       | `acid,lava,poison`                        | List of materials that inflict damage on contact.                           |
| `materials_how_much_damage`   | `0.004,0.0005,0.001`                      | The amount of damage taken from each material in `materials_that_damage`.   |

#### `damage_multipliers`

Specific multipliers for different damage types.

| Damage Type | Multiplier | Description                                     |
| :---------- | :--------- | :---------------------------------------------- |
| `projectile`| `0.9`      | Damage taken from projectiles.                  |
| `explosion` | `0.3`      | Damage taken from explosions.                   |
| `fire`      | `1.5`      | Damage taken from fire.                         |
| `slice`     | `0.2`      | Damage taken from slicing attacks.              |
| `ice`       | `-1`       | Immunity to ice damage (negative value implies immunity). |

### `SpriteComponent`

Determines the visual appearance of the entity.

| Attribute     | Value                               | Description                               |
| :------------ | :---------------------------------- | :---------------------------------------- |
| `image_file`  | `data/enemies_gfx/skullmage.xml`    | Path to the sprite definition file.       |
| `offset_x`    | `0`                                 | Horizontal offset for the sprite.         |
| `offset_y`    | `0`                                 | Vertical offset for the sprite.           |

### `CharacterPlatformingComponent`

Controls movement and jumping abilities.

| Attribute         | Value | Description                               |
| :---------------- | :---- | :---------------------------------------- |
| `jump_velocity_y` | `-12` | The vertical velocity applied when jumping. |
| `run_velocity`    | `18`  | The horizontal movement speed.            |

## Special Components

### `ParticleEmitterComponent`

Responsible for emitting visual particles.

| Attribute                   | Value   | Description                                                              |
| :-------------------------- | :------ | :----------------------------------------------------------------------- |
| `emitted_material_name`     | `spark_white` | The material of the particles being emitted.                             |
| `gravity.y`                 | `0.0`   | Vertical gravity applied to particles.                                   |
| `lifetime_min`              | `0.5`   | Minimum lifetime of emitted particles.                                   |
| `lifetime_max`              | `1.5`   | Maximum lifetime of emitted particles.                                   |
| `count_min`                 | `1`     | Minimum number of particles emitted per emission.                        |
| `count_max`                 | `3`     | Maximum number of particles emitted per emission.                        |
| `render_on_grid`            | `1`     | Whether particles should be rendered on the game grid.                   |
| `fade_based_on_lifetime`    | `1`     | Whether particles fade out as their lifetime decreases.                  |
| `x_pos_offset_min`          | `-5`    | Minimum horizontal offset for particle emission.                         |
| `y_pos_offset_min`          | `-12`   | Minimum vertical offset for particle emission.                           |
| `x_pos_offset_max`          | `5`     | Maximum horizontal offset for particle emission.                         |
| `y_pos_offset_max`          | `4`     | Maximum vertical offset for particle emission.                           |
| `cosmetic_force_create`     | `0`     | Whether particles are purely cosmetic and don't affect gameplay.         |
| `emission_interval_min_frames`| `2`     | Minimum frames between particle emissions.                               |
| `emission_interval_max_frames`| `4`     | Maximum frames between particle emissions.                               |
| `emit_cosmetic_particles`   | `1`     | Whether to emit cosmetic particles.                                      |
| `is_emitting`               | `1`     | Whether the particle emitter is currently active.                        |

### `LightComponent`

Adds a light source to the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `r`       | `120` | Red component of the light color.         |
| `g`       | `180` | Green component of the light color.       |
| `b`       | `220` | Blue component of the light color.        |
| `radius`  | `64`  | The radius of the light source.           |

### `AudioLoopComponent`

Manages looping sound effects for the entity.

| Attribute   | Value                                | Description                               |
| :---------- | :----------------------------------- | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`    | The audio bank file containing the sound. |
| `event_name`| `animals/wizard/movement_loop`       | The specific sound event to play.         |
| `auto_play` | `1`                                  | Whether the sound plays automatically.    |

### `Base file="data/entities/misc/material_converter_freeze.xml"`

This entity inherits functionality from a base file, specifically for freezing materials.

#### `MagicConvertMaterialComponent`

Configures the material conversion effect.

| Attribute     | Value | Description                                                                 |
| :------------ | :---- | :-------------------------------------------------------------------------- |
| `steps_per_frame` | `20`  | Number of conversion steps to perform per frame.                            |
| `loop`        | `1`   | Whether the conversion effect should loop.                                  |
| `is_circle`   | `1`   | Whether the conversion area is circular.                                    |
| `radius`      | `30`  | The radius of the material conversion effect.                               |
| `kill_when_finished`| `0`   | Whether the effect should be removed once completed (0 = no).               |
| `extinguish_fire`| `1`   | Whether the effect should extinguish fire.                                  |