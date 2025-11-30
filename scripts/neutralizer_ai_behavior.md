---
title: Neutralizer AI Behavior
category: scripts
---

---

# Neutralizer AI Behavior

This script modifies the ranged attack behavior of entities with an `AnimalAIComponent` based on the presence of entities tagged as "neutralizer_target".

## Core Logic

The script checks for the existence of entities with the tag "neutralizer_target".

*   **If "neutralizer_target" entities are found:**
    *   The `attack_ranged_entity_file` is set to `data/entities/projectiles/machinegun_bullet_roboguard_big.xml`.
    *   The `attack_ranged_frames_between` is set to `20`.
*   **If no "neutralizer_target" entities are found:**
    *   The `attack_ranged_entity_file` is set to `data/entities/projectiles/neutralizershot.xml`.
    *   The `attack_ranged_frames_between` is set to `90`.

## Key Components Modified

The script directly interacts with the `AnimalAIComponent` of an entity.

### `AnimalAIComponent` Attributes

| Attribute                     | Description                                                                                             |
| :---------------------------- | :------------------------------------------------------------------------------------------------------ |
| `attack_ranged_entity_file`   | The XML file path for the projectile to be fired in a ranged attack.                                    |
| `attack_ranged_frames_between`| The number of game frames to wait between ranged attacks.                                               |

## Usage

This script is intended to be attached to entities that should exhibit this conditional ranged attack behavior. The presence of entities with the "neutralizer_target" tag will dynamically alter their offensive capabilities.