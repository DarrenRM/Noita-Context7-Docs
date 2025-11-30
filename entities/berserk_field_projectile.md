---
title: Berserk Field Projectile
category: entities
---

# Berserk Field Projectile

This document details the `berserk_field.xml` entity, which defines a projectile that creates a berserk field.

## Key Components and Attributes

### GameAreaEffectComponent

This component defines the area of effect for the berserk field.

*   **radius**: The radius of the berserk field.

### ParticleEmitterComponent (x2)

These components are responsible for emitting cosmetic particles around the projectile.

*   **emitted_material_name**: The material of the emitted particles (`spark_red`).
*   **lifetime_min**, **lifetime_max**: The minimum and maximum lifetime of the emitted particles.
*   **count_min**, **count_max**: The minimum and maximum number of particles emitted per burst.
*   **render_on_grid**: Whether particles should render on the game grid.
*   **fade_based_on_lifetime**: If particles should fade as their lifetime ends.
*   **area_circle_radius.max**: The maximum radius for particle emission.
*   **cosmetic_force_create**: Whether particles are forced to be cosmetic.
*   **airflow_force**, **airflow_time**, **airflow_scale**: Parameters controlling airflow effects on particles.
*   **emission_interval_min_frames**, **emission_interval_max_frames**: Controls the interval between particle emissions.
*   **emit_cosmetic_particles**: Whether to emit cosmetic particles.
*   **is_emitting**: Whether the emitter is active.

### Base Component (`base_field.xml`)

This entity inherits properties from `base_field.xml`, providing a foundation for field projectiles.

#### SpriteComponent

Defines the visual appearance of the projectile.

*   **image_file**: The sprite file used for the projectile (`data/projectiles_gfx/blast_berserk.xml`).

#### SpriteParticleEmitterComponent

Emits specific sprite-based particles.

*   **sprite_file**: The sprite file for these particles (`data/particles/berserk_0$[1-4].xml`). The `$[1-4]` indicates a range of sprites.

#### ProjectileComponent

Defines the projectile's behavior and effects.

*   **damage_game_effect_entities**: Specifies the game effect entities applied by the projectile. In this case, it applies `data/entities/misc/effect_berserk.xml`.
*   **config_explosion**: Configuration for the projectile's explosion.
    *   **explosion_sprite**: The sprite used for the explosion (`data/particles/blast_out_berserk.xml`).

## Summary

The `berserk_field.xml` entity creates a projectile that, upon impact or activation, generates a berserk field. This field is visually represented by red sparks and has a defined radius. The projectile itself uses a specific sprite and triggers a berserk effect on entities within its area of influence, likely causing them to enter a berserk state. The explosion of the projectile also uses a distinct sprite.