---
title: Teleportation Field Projectile
category: entities
---

# Teleportation Field Projectile

This document describes the `teleportation_field.xml` entity, which defines a projectile that creates a teleportation field. This field can affect enemies by teleporting them.

## Key Components and Attributes

### GameAreaEffectComponent

This component defines the area of effect for the projectile.

*   **radius**: The radius of the area of effect.

### ParticleEmitterComponent (x2)

These components are responsible for emitting visual particles to represent the field.

*   **emitted_material_name**: The material used for the emitted particles (e.g., `spark_blue`).
*   **lifetime_min/max**: The minimum and maximum lifetime of individual particles.
*   **count_min/max**: The minimum and maximum number of particles emitted per burst.
*   **fade_based_on_lifetime**: Whether particles fade out as their lifetime ends.
*   **area_circle_radius.max**: The maximum radius for particle emission.
*   **airflow_force/time/scale**: Parameters controlling how airflow affects the particles.
*   **emission_interval_min/max_frames**: Controls the timing of particle emissions.
*   **emit_cosmetic_particles**: Whether to emit cosmetic particles.
*   **is_emitting**: Whether the emitter is active.

### Base Component (`base_field.xml`)

This indicates that the entity inherits properties from a base field projectile.

#### SpriteComponent

Defines the visual appearance of the projectile.

*   **image\_file**: The path to the sprite image file (e.g., `data/projectiles_gfx/blast_teleportation.xml`).

#### SpriteParticleEmitterComponent

Emits particles that are sprites themselves, contributing to the visual effect.

*   **sprite\_file**: The path to the sprite file for these particles (e.g., `data/particles/teleparticle.xml`).
*   **lifetime**: The duration of these sprite particles.
*   **scale.x/y**: The initial scale of the sprite particles.
*   **color\_change.a**: The change in alpha (transparency) over the particle's lifetime.
*   **scale\_velocity.x/y**: How the scale of the particles changes over time.
*   **randomize\_velocity.min/max\_x/y**: Randomization applied to particle velocity.
*   **velocity\_always\_away\_from\_center**: Whether particles are always emitted away from the center.

#### ProjectileComponent

Defines the core projectile behavior and effects.

*   **damage\_game\_effect\_entities**: A comma-separated list of entities that apply game effects when the projectile hits. In this case, it applies `effect_teleportation_enemy.xml`.
*   **friendly\_fire**: Whether the projectile can affect friendly entities. `1` means it can.
*   **collide\_with\_shooter\_frames**: The number of frames the projectile will collide with its shooter. `0` means it won't collide.
*   **config\_explosion**: Configuration for any explosion effect associated with the projectile.
    *   **explosion\_sprite**: The sprite used for the explosion effect (e.g., `data/particles/blast_out_teleportation.xml`).