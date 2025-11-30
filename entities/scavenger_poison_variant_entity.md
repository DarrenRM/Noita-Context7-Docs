---
title: Scavenger (Poison Variant) Entity
category: entities
---

# Scavenger (Poison Variant) Entity

This document details the configuration for the "Scavenger (Poison Variant)" entity in Noita, primarily focusing on its combat, movement, and AI behaviors.

## Core Attributes

The Scavenger (Poison Variant) is a flying enemy with distinct offensive and defensive capabilities.

### `Base` Entity Configuration

This entity inherits from `base_enemy_flying.xml` and `base_jetpack.xml`, gaining fundamental flying enemy traits and jetpack mechanics.

### `AnimalAIComponent`

This component governs the creature's artificial intelligence and behavior.

| Attribute                       | Value                                     | Description                                                                 |
| :------------------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`                      | `1`                                       | Enables the AI component.                                                   |
| `preferred_job`                 | `JobDefault`                              | The default job assigned to this creature.                                  |
| `escape_if_damaged_probability` | `60`                                      | Percentage chance to flee when damaged.                                     |
| `attack_melee_damage_min`       | `0.4`                                     | Minimum damage dealt by melee attacks.                                      |
| `attack_melee_damage_max`       | `0.7`                                     | Maximum damage dealt by melee attacks.                                      |
| `creature_detection_range_x`    | `500`                                     | Horizontal range for detecting other creatures.                             |
| `creature_detection_range_y`    | `500`                                     | Vertical range for detecting other creatures.                               |
| `creature_detection_angular_range_deg` | `60`                                      | Angular range (in degrees) for creature detection.                          |
| `attack_melee_max_distance`     | `10`                                      | Maximum distance for initiating a melee attack.                             |
| `food_material`                 | `meat`                                    | The material this creature considers food.                                  |
| `needs_food`                    | `0`                                       | Whether the creature requires food to survive.                              |
| `sense_creatures`               | `1`                                       | Enables the creature to sense other creatures.                              |
| `can_fly`                       | `1`                                       | Allows the creature to fly.                                                 |
| `aggressiveness_min`            | `1`                                       | Minimum aggressiveness level.                                               |
| `aggressiveness_max`            | `80`                                      | Maximum aggressiveness level.                                               |

### `DamageModelComponent`

Defines the health and damage resistances/vulnerabilities of the entity.

| Attribute                       | Value                                                                                             | Description