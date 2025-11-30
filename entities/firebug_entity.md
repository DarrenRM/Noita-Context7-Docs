---
title: Firebug Entity
category: entities
---

# Firebug Entity

This document details the `firebug.xml` entity, a flying, aggressive creature in Noita.

## Core Components

The Firebug is built upon a `Base` entity, inheriting its fundamental properties. Key components and their significant attributes are outlined below.

### AnimalAIComponent

Manages the creature's behavior, including detection, movement, and attacks.

| Attribute                      | Value                                       | Description                                                                 |
| :----------------------------- | :------------------------------------------ | :-------------------------------------------------------------------------- |
| `attack_ranged_frames_between` | `40`                                        | Delay between ranged attacks in frames.                                     |
| `attack_ranged_entity_file`    | `data/entities/projectiles/fireball_firebug.xml` | The projectile entity used for ranged attacks.                              |
| `attack_ranged_enabled`        | `1`                                         | Enables ranged attacks.                                                     |
| `attack_ranged_max_distance`   | `130`                                       | Maximum distance from which it can perform a ranged attack.                 |
| `attack_dash_enabled`          | `1`                                         | Enables a dash attack.                                                      |
| `creature_detection_range_x`   | `300`                                       | Horizontal range for detecting creatures.                                   |
| `creature_detection_range_y`   | `300`                                       | Vertical range for detecting creatures.                                     |
| `can_fly`                      | `1`                                         | Allows the creature to fly.                                                 |
| `needs_food`                   | `0`                                         | Indicates the creature does not require food.                               |

### DamageModelComponent

Defines the creature's health and how it takes damage.

| Attribute                      | Value                                                                                             | Description