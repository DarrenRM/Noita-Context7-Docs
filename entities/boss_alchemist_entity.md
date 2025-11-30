---
title: Boss Alchemist Entity
category: entities
---

# Boss Alchemist Entity

This document details the configuration of the Boss Alchemist entity in Noita, focusing on its core attributes and behaviors relevant to AI-assisted modding.

## Core Attributes

The Boss Alchemist is a formidable enemy with several key attributes defining its combat and movement capabilities.

### Base Entity Configuration

The entity inherits from `base_enemy_basic.xml`, providing a foundation for its general enemy properties.

### `AnimalAIComponent`

This component governs the Alchemist's artificial intelligence and combat actions.

| Attribute                  | Value                                                              | Description                                                                                                |
| :------------------------- | :----------------------------------------------------------------- | :--------------------------------------------------------------------------------------------------------- |
| `preferred_job`            | `JobDefault`                                                       | The default job assigned to this AI.                                                                       |
| `attack_melee_enabled`     | `0`                                                                | Melee attacks are disabled.                                                                                |
| `creature_detection_range_x` | `400`                                                              | Horizontal range for detecting creatures.                                                                  |
| `creature_detection_range_y` | `400`                                                              | Vertical range for detecting creatures.                                                                    |
| `food_material`            | `blood`                                                            | The material the creature consumes for sustenance (though `needs_food` is `0`).                            |
| `needs_food`               | `0`                                                                | The creature does not require food to survive.                                                             |
| `sense_creatures`          | `1`                                                                | The creature actively senses other creatures.                                                              |
| `attack_ranged_enabled`    | `1`                                                                | Ranged attacks are enabled.                                                                                |
| `can_fly`                  | `1`                                                                | The creature is capable of flight.                                                                         |
| `attack_ranged_entity_file`| `data/entities/animals/boss_alchemist/wand_orb.xml`                | Specifies the entity file used for its ranged attacks (a wand orb).                                        |
| `attack_ranged_action_frame`| `5`                                                                | The frame at which the ranged attack animation is triggered.                                               |
| `attack_ranged_frames_between`| `180`                                                              | The number of frames between consecutive ranged attacks.                                                   |
| `attack_ranged_max_distance`| `240`                                                              | The maximum distance at which the creature will perform a ranged attack.                                   |

### `DamageModelComponent`

Defines the Alchemist's health, resistances, and damage-related properties.

| Attribute                 | Value                               | Description