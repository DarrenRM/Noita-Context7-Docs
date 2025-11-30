---
title: Levitation Field Projectile
category: entities
---

# Levitation Field Projectile

This document details the `levitation_field.xml` entity, which defines a projectile that creates a levitation field.

## Core Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: The radius of the area affected by the levitation field.

### ParticleEmitterComponent (x2)
These components are responsible for emitting visual "spark" particles to represent the levitation field.

*   **emitted_material_name**: Specifies the material of the emitted particles ("spark").
*   **gravity.y**: Controls the vertical gravity applied to the particles (set to 0.0 for no gravity).
*   **lifetime_min/max**: The minimum and maximum duration each particle exists.
*   **count_min/max**: The range for the number of particles emitted per emission.
*   **render_on_grid**: Whether the particles should be rendered on the game grid.
*   **fade_based_on_lifetime**: If particles fade out as their lifetime decreases.
*   **area_circle_radius.min/max**: Defines the radial area from which particles can be emitted.
*   **cosmetic_force_create**: If particles are created purely for cosmetic purposes.
*   **airflow_force/time/scale**: Parameters controlling how airflow affects the particles.
*   **emission_interval_min/max_frames**: The frame range between particle emissions.
*   **emit_cosmetic_particles**: Whether to emit cosmetic particles.
*   **is_emitting**: If the emitter is currently active.

### Base Component
This entity inherits its base properties from `base_field.xml`.

#### SpriteComponent
*   **image_file**: Specifies the graphical asset for the projectile's sprite (`data/projectiles_gfx/blast_levitation.xml`).

#### SpriteParticleEmitterComponent
This component adds additional visual flair with "shine" particles.

*   **sprite_file**: The particle sprite definition (`data/particles/shine_levitation.xml`).
*   **randomize_position.min/max_x/y**: Defines the area within which these particles are randomly positioned relative to the projectile.

#### ProjectileComponent
Defines the projectile's behavior and interactions.

*   **friendly_fire**: If the projectile can affect friendly entities (set to 1, meaning it can).
*   **collide_with_shooter_frames**: The number of frames the projectile will ignore collisions with its shooter.
*   **damage_game_effect_entities**: Specifies entities that apply game effects when hit. In this case, it points to `data/entities/misc/effect_levitation.xml`, which likely handles the actual levitation logic.

##### config_explosion
*   **explosion_sprite**: The sprite used for any explosion effect associated with the projectile (`data/particles/blast_out_levitation.xml`).

### LevitationComponent
This is the core component that enables the levitation effect.

*   **radius**: The radius of the levitation effect.
*   **entity_force**: The force applied to entities within the levitation radius to lift them.
*   **box2d_force**: A force applied to physics bodies within the levitation radius.