---
title: Charm Field Projectile
category: entities
---

# Charm Field Projectile

This document describes the `charm_field.xml` entity, which defines a projectile that creates a charm field.

## Core Functionality

The `charm_field.xml` entity represents a projectile that, upon impact or expiration, generates a charm effect in an area. It utilizes several components to achieve its visual and functional aspects.

## Key Components and Attributes

### GameAreaEffectComponent

This component defines the area of effect for the charm.

*   **radius**: `28` - The radius of the charm field.

### ParticleEmitterComponent (x2)

These components are responsible for emitting visual particles that contribute to the charm field's appearance. Both emitters use the `plasma_fading_pink` material.

**Emitter 1:**

*   **emitted\_material\_name**: `plasma_fading_pink`
*   **lifetime\_min**: `0.5`
*   **lifetime\_max**: `1.5`
*   **count\_min**: `2`
*   **count\_max**: `4`
*   **area\_circle\_radius.max**: `28`
*   **airflow\_force**: `0.5`

**Emitter 2:**

*   **emitted\_material\_name**: `plasma_fading_pink`
*   **lifetime\_min**: `0.5`
*   **lifetime\_max**: `1.5`
*   **count\_min**: `4`
*   **count\_max**: `4`
*   **area\_circle\_radius.min**: `28`
*   **area\_circle\_radius.max**: `28`
*   **airflow\_force**: `0.3`

### Base Component

This entity inherits functionality from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent

*   **image\_file**: `data/projectiles_gfx/blast_charm.xml` - Defines the visual sprite for the projectile itself.

#### SpriteParticleEmitterComponent

*   **sprite\_file**: `data/particles/charm.xml` - Specifies the particle effect associated with the charm.

#### ProjectileComponent

This is a crucial component that defines the projectile's behavior and effects.

*   **damage\_game\_effect\_entities**: `data/entities/misc/effect_charm.xml` - This attribute links to an entity that defines the actual "charm" game effect applied to targets within the field.
*   **config\_explosion**: Defines the visual effect upon the projectile's destruction or impact.
    *   **explosion\_sprite**: `data/particles/blast_out_charm.xml` - The sprite used for the explosion effect.

### VariableStorageComponent

*   **name**: `projectile_file`
*   **value\_string**: `data/entities/projectiles/deck/charm_field.xml` - Stores the path to this entity's own file, likely for internal referencing.

## Summary

The `charm_field.xml` entity is a projectile that visually manifests as a pink plasma field and applies a charm effect to entities within its radius. Its behavior is a combination of visual particle emission, a defined area of effect, and the application of a specific game effect defined in `effect_charm.xml`.