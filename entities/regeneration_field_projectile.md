---
title: Regeneration Field Projectile
category: entities
---

# Regeneration Field Projectile

This entity defines a projectile that creates a regeneration field. It applies a healing effect to entities within its radius and has a distinct visual and audio presence.

## Key Components

### GameAreaEffectComponent
This component defines the area of effect for the entity.

*   **radius**: The radius of the area of effect.

### ParticleEmitterComponent (x2)
These components are responsible for emitting visual particles to represent the field.

*   **emitted_material_name**: The material used for the emitted particles (e.g., `spark_green`).
*   **lifetime_min/max**: The minimum and maximum lifetime of individual particles.
*   **count_min/max**: The minimum and maximum number of particles emitted per burst.
*   **render_on_grid**: Whether particles should be rendered on the game grid.
*   **fade_based_on_lifetime**: If particles should fade out as their lifetime ends.
*   **area_circle_radius.max**: The maximum radius for particle emission.
*   **cosmetic_force_create**: Whether to force the creation of cosmetic particles.
*   **airflow_force/time/scale**: Parameters controlling the airflow effect on particles.
*   **emission_interval_min/max_frames**: The frame interval between particle emissions.
*   **emit_cosmetic_particles**: Whether to emit cosmetic particles.
*   **is_emitting**: Whether the emitter is currently active.

### Base (Inherited)
This entity inherits properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent
*   **image_file**: Specifies the graphical representation of the projectile.

#### LifetimeComponent
*   **lifetime**: The duration the projectile (and its field) will exist.

#### SpriteParticleEmitterComponent
*   **sprite_file**: The particle effect to be applied.
*   **color.r/g/b/a**: The initial color of the particles.

#### ProjectileComponent
*   **damage_game_effect_entities**: The entity that defines the game effect applied by the projectile (in this case, regeneration).
*   **friendly_fire**: Whether the projectile affects friendly entities.
*   **collide_with_shooter_frames**: Frames before the projectile can collide with its shooter.
*   **config_explosion**: Defines the visual effect upon the projectile's destruction.

#### AudioLoopComponent
*   **file**: The audio bank containing the sound event.
*   **event_name**: The specific audio event to play for the regeneration field loop.
*   **auto_play**: Whether the sound should start automatically.