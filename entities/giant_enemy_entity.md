---
title: Giant Enemy Entity
category: entities
---

# Giant Enemy Entity

This document details the configuration for the "Giant" enemy entity in Noita, primarily focusing on its AI, combat, and physical attributes.

## Core Components

The Giant entity inherits from `base_enemy_basic.xml` and utilizes several key components to define its behavior and appearance.

### AnimalAIComponent

This component governs the Giant's artificial intelligence, including its combat capabilities and creature detection.

| Attribute                     | Value                                     | Description                                                                 |
| :---------------------------- | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                    | `1`                                       | Enables the AI component.                                                   |
| `preferred_job`               | `JobDefault`                              | The default job assigned to this AI.                                        |
| `escape_if_damaged_probability` | `0`                                       | Probability of escaping when damaged (0 means it never flees).              |
| `attack_melee_damage_min`     | `0.4`                                     | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`     | `0.7`                                     | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`  | `600`                                     | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`  | `400`                                     | Vertical range for detecting creatures.                                     |
| `needs_food`                  | `0`                                       | Whether the creature requires food (0 means it does not).                   |
| `sense_creatures`             | `1`                                       | Enables the creature to sense other creatures.                              |
| `attack_ranged_enabled`       | `1`                                       | Enables ranged attacks.                                                     |
| `attack_melee_enabled`        | `1`                                       | Enables melee attacks.                                                      |
| `can_fly`                     | `0`                                       | Whether the creature can fly (0 means it cannot).                           |
| `attack_ranged_action_frame`  | `4`                                       | The animation frame at which a ranged attack is initiated.                  |
| `attack_ranged_entity_file`   | `data/entities/projectiles/pebble.xml`    | The entity file used for ranged projectiles.                                |
| `attack_ranged_frames_between`| `100`                                     | Number of animation frames between ranged attacks.                          |
| `attack_ranged_offset_y`      | `-12`                                     | Vertical offset for the origin of ranged attacks.                           |
| `attack_ranged_max_distance`  | `600`                                     | Maximum distance for ranged attacks.                                        |

### DamageModelComponent

Defines the Giant's health, resistances, and how it reacts to damage and environmental hazards.

| Attribute                     | Value