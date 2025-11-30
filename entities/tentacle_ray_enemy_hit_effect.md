---
title: Tentacle Ray Enemy Hit Effect
category: entities
---

# Tentacle Ray Enemy Hit Effect

This entity defines the visual and functional effect that occurs when a "tentacle ray enemy" is hit.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is struck.

*   **`effect_hit`**: Specifies the type of effect to trigger.
    *   `LOAD_UNIQUE_CHILD_ENTITY`: Indicates that a specific child entity should be loaded as the hit effect.
*   **`value_string`**: Defines the path to the entity that will be loaded as the hit effect.
    *   `data/entities/misc/tentacle_ray_enemy.xml`: This is the entity that will be instantiated upon impact.

## Usage

This entity is typically referenced by other entities that deal damage to the "tentacle ray enemy." When damage is applied, this `hitfx_tentacle_ray_enemy.xml` entity is activated, causing the `tentacle_ray_enemy.xml` entity to be spawned at the point of impact, visually representing the hit.