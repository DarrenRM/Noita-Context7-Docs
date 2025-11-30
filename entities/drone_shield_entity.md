---
title: Drone Shield Entity
category: entities
---

# Drone Shield Entity

This document describes the `drone_shield.xml` entity, which represents a shield component for drones in Noita.

## Entity Structure

The entity is defined by a root `<Entity>` tag.

### Base Component

*   **`file`**: `data/entities/animals/drone_shield.xml` - Specifies the base file for inheritance.
*   **`include_children`**: `1` - Indicates that child entities should also be included.

### DamageModelComponent

This component defines the health and damage properties of the drone shield.

*   **`hp`**: `16` - The current health points of the shield.
*   **`max_hp`**: `16` - The maximum health points of the shield.
*   **`minimum_knockback_force`**: `100000` - A very high value, suggesting the shield is resistant to knockback.

#### Damage Multipliers

*   **`projectile`**: `0.0` - The shield is immune to damage from projectiles.

### Child Entity: Shield Effect

This nested entity applies a special effect to the shield.

#### InheritTransformComponent

*   This component ensures the child entity inherits the transform (position, rotation, scale) of its parent.

#### GameEffectComponent

This component applies a game effect to the entity.

*   **`effect`**: `PROTECTION_FREEZE` - The effect applied is protection against freezing.
*   **`frames`**: `-1` - The effect lasts indefinitely (until removed or the entity is destroyed).