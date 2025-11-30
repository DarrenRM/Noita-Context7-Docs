---
title: Gravity Field Enemy Hit Effect
category: entities
---

# Gravity Field Enemy Hit Effect

This entity defines the visual and functional effect that occurs when an enemy is hit, specifically triggering the creation of a gravity field.

## Key Components

### HitEffectComponent

This component dictates what happens when the entity is hit.

| Attribute        | Description                                                                 |
| :--------------- | :-------------------------------------------------------------------------- |
| `effect_hit`     | Specifies the type of effect to apply on hit. `LOAD_UNIQUE_CHILD_ENTITY` means a new entity will be spawned. |
| `value_string`   | The path to the entity that will be spawned as a child effect. In this case, it's `data/entities/misc/gravity_field_enemy.xml`, which likely defines the gravity field itself. |