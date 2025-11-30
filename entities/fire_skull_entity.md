---
title: Fire Skull Entity
category: entities
---

# Fire Skull Entity

This document details the configuration of the Fire Skull entity in Noita, focusing on its AI, combat, and visual properties for AI-assisted modding.

## Core Attributes

The Fire Skull is a flying enemy with a focus on dash attacks and a distinct fiery appearance.

### Base Entity Configuration

The Fire Skull inherits its core functionality from `base_enemy_flying.xml`.

### Animal AI Component

This component governs the creature's behavior.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `attack_ranged_enabled`   | `0`     | Ranged attacks are disabled.                                                |
| `attack_dash_enabled`     | `1`     | Dash attacks are enabled.                                                   |
| `attack_ranged_frames_between` | `20`    | Frames to wait between ranged attacks (not applicable here).                |
| `can_fly`                 | `1`     | The entity is capable of flight.                                            |
| `aggressiveness_min`      | `0`     | Minimum aggressiveness level.                                               |
| `aggressiveness_max`      | `50`    | Maximum aggressiveness level.                                               |
| `needs_food`              | `0`     | The entity does not require food.                                           |

### Damage Model Component

Defines the entity's health and how it interacts with damage and materials.

| Attribute                     | Value                                                                                             | Description