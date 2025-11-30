---
title: Miner Hell Entity
category: entities
---

# Miner Hell Entity

This document details the configuration of the "Miner Hell" entity in Noita, focusing on attributes relevant to AI-assisted modding.

## Core Attributes

The Miner Hell is a hostile creature with distinct offensive and defensive capabilities.

### AnimalAIComponent

This component governs the creature's behavior, including detection, combat, and movement.

| Attribute                      | Value                                     | Description                                                                 |
| :----------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                     | `1`                                       | Enables the AI component.                                                   |
| `preferred_job`                | `JobDefault`                              | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability`| `40`                                      | Percentage chance to flee when damaged.                                     |
| `attack_melee_damage_min`      | `0.4`                                     | Minimum damage for melee attacks.                                           |
| `attack_melee_damage_max`      | `0.7`                                     | Maximum damage for melee attacks.                                           |
| `creature_detection_range_x`   | `300`                                     | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`   | `300`                                     | Vertical range for detecting other creatures.                               |
| `food_material`                | `meat`                                    | The material this creature considers food.                                  |
| `needs_food`                   | `1`                                       | Whether the creature requires food to survive.                              |
| `sense_creatures`              | `1`                                       | Enables the creature to sense other creatures.                              |
| `attack_ranged_enabled`        | `1`                                       | Enables ranged attacks.                                                     |
| `attack_melee_enabled`         | `1`                                       | Enables melee attacks.                                                      |
| `attack_ranged_entity_file`    | `data/entities/projectiles/tnt_hell.xml`  | The projectile entity file used for ranged attacks.                         |
| `attack_ranged_entity_count_min`| `6`                                       | Minimum number of projectiles fired per ranged attack.                      |
| `attack_ranged_entity_count_max`| `14`                                      | Maximum number of projectiles fired per ranged attack.                      |
| `attack_ranged_frames_between` | `60`                                      | Frames between ranged attacks.                                              |

### DamageModelComponent

Defines the creature's health, resistances, and how it reacts to damage.

| Attribute                      | Value                                     | Description                                                                 |
| :----------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `hp`                           | `3.0`                                     | Hit points of the creature.                                                 |
| `blood_spray_material`         | `liquid_fire`                             | The material of the blood spray when damaged.                               |
| `blood_material`               | `liquid_fire`                             | The material of the blood when damaged.                                     |
| `fire_probability_of_ignition` | `0`                                       | Probability of igniting from fire damage.                                   |

#### damage_multipliers

Specific multipliers for different damage types.

| Damage Type | Multiplier |
| :---------- | :--------- |
| `projectile`| `0.6`      |
| `explosion` | `0.6`      |
| `slice`     | `1`        |
| `holy`      | `2.0`      |

### SpriteComponent

Determines the visual representation of the entity.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `image_file`| `data/enemies_gfx/miner_hell.xml`   | Path to the sprite's XML definition.      |

### PathFindingComponent

Configures how the creature navigates the game world.

| Attribute                   | Value | Description                                     |
| :-------------------------- | :---- | :---------------------------------------------- |
| `can_jump`                  | `1`   | Allows the creature to jump.                    |
| `jump_speed`                | `100` | The speed at which the creature jumps.          |
| `initial_jump_max_distance_x`| `60`  | Maximum horizontal distance of a jump.          |
| `initial_jump_max_distance_y`| `60`  | Maximum vertical distance of a jump.            |
| `can_swim_on_surface`       | `1`   | Allows swimming on the surface of liquids.      |
| `can_dive`                  | `1`   | Allows diving into liquids.                     |

### CharacterPlatformingComponent

Defines movement parameters for characters.

| Attribute     | Value | Description                               |
| :------------ | :---- | :---------------------------------------- |
| `jump_velocity_y`| `-12` | The vertical velocity applied when jumping. |
| `run_velocity`| `16`  | The horizontal movement speed.            |

## Other Notable Components

### LightComponent

Adds a light source to the entity.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `radius`  | `50`  | The radius of the light.                  |

### AudioComponent

Manages the sound effects associated with the entity.

| Attribute   | Value                           | Description                               |
| :---------- | :------------------------------ | :---------------------------------------- |
| `file`      | `data/audio/Desktop/animals.bank`| The audio bank file.                      |
| `event_root`| `animals/miner`                 | The root event name for miner sounds.     |

### GameEffectComponent

Applies a persistent game effect to the entity.

| Attribute | Value              | Description                               |
| :-------- | :----------------- | :---------------------------------------- |
| `effect`  | `ALLERGY_RADIOACTIVE`| The game effect applied.                  |
| `frames`  | `-1`               | Duration of the effect (-1 for infinite). |