---
title: Tank Super Entity
category: entities
---

# Tank Super Entity

This document describes the `tank_super.xml` entity, a powerful robotic enemy in Noita.

## Key Attributes

### Base Entity

*   **`file`**: `data/entities/animals/tank_super.xml` - Specifies the base XML file for this entity.
*   **`include_children`**: `1` - Indicates that child entities defined within this file should also be included.

### Damage Component (`DamageModelComponent`)

This component defines the health and damage resistance of the Tank Super.

*   **`hp`**: `18` - The current health points of the entity.
*   **`max_hp`**: `18` - The maximum health points the entity can have.
*   **`minimum_knockback_force`**: `100000` - A very high value, suggesting significant resistance to knockback effects.

#### Damage Multipliers (`damage_multipliers`)

*   **`projectile`**: `0.0` - The Tank Super is immune to damage from projectiles.

### Game Effect Component (`GameEffectComponent`)

This component applies special effects to the entity.

*   **`effect`**: `PROTECTION_FREEZE` - The entity is immune to freezing effects.
*   **`frames`**: `-1` - The freeze protection is permanent (infinite duration).