---
title: Telepathy Field Projectile
category: entities
---

# Telepathy Field Projectile

This document describes the `telepathy_field.xml` entity, which defines a projectile used for the "Telepathy" spell in Noita.

## Core Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: `28` - The radius of the telepathy field.

### Base Component
This entity inherits its base properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent
Defines the visual appearance of the projectile.

*   **image\_file**: `data/projectiles_gfx/blast_telepathy.xml` - Specifies the sprite used for the telepathy blast.

#### SpriteParticleEmitterComponent
Manages the particles emitted by the projectile.

*   **sprite\_file**: `data/particles/ray.xml` - The sprite used for the emitted particles.
*   **gravity.y**: `0` - No vertical gravity applied to particles.
*   **color\_change.a**: `-3` - Controls the alpha (transparency) change of particles over time.
*   **randomize\_velocity.min\_x**: `-40`
*   **randomize\_velocity.max\_x**: `40`
*   **randomize\_velocity.min\_y**: `-40`
*   **randomize\_velocity.max\_y**: `40` - These attributes define the random velocity applied to particles in X and Y directions.
*   **randomize\_rotation.min**: `0`
*   **randomize\_rotation.max**: `0` - No random rotation for particles.
*   **randomize\_angular\_velocity.min**: `0`
*   **randomize\_angular\_velocity.max**: `0` - No random angular velocity for particles.
*   **use\_velocity\_as\_rotation**: `1` - Particle rotation is determined by their velocity.

#### ProjectileComponent
Defines the projectile's behavior and interactions.

*   **damage\_game\_effect\_entities**: `data/entities/misc/effect_telepathy.xml,` - Specifies the game effect applied when the projectile hits. This likely triggers the telepathy effect on entities.
*   **friendly\_fire**: `1` - The projectile can affect friendly entities.
*   **collide\_with\_shooter\_frames**: `0` - The projectile does not collide with the entity that fired it for the first few frames.

##### ConfigExplosion
Defines the visual effect upon explosion.

*   **explosion\_sprite**: `data/particles/blast_out_telepathy.xml` - The sprite used for the explosion effect.