---
title: Gazer Enemy Entity
category: entities
---

# Gazer Enemy Entity

This document details the configuration for the Gazer enemy entity in Noita, focusing on its attributes relevant to AI-assisted modding.

## Base Entity Configuration

The Gazer inherits from `base_enemy_flying.xml`, indicating its aerial capabilities and general enemy behavior.

### `AnimalAIComponent`

This component governs the Gazer's artificial intelligence and combat behaviors.

| Attribute                 | Description                                                              |
| :------------------------ | :----------------------------------------------------------------------- |
| `attack_ranged_entity_file` | Specifies the projectile entity used for ranged attacks (e.g., `lavashot.xml`). |
| `attack_ranged_enabled`   | Enables ranged attacks (1 for enabled, 0 for disabled).                  |
| `attack_ranged_action_frame` | The frame within the attack animation when the projectile is fired.      |
| `attack_dash_enabled`     | Controls whether the Gazer can perform a dash attack (0 for disabled).   |
| `attack_ranged_frames_between` | The number of frames to wait between ranged attacks.                     |
| `can_fly`                 | Indicates if the entity can fly (1 for enabled).                         |

### `DamageModelComponent`

Defines the Gazer's health, damage resistances, and how it reacts to damage.

| Attribute                     | Description