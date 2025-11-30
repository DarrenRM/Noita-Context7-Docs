---
title: Regeneration Field Long Projectile
category: entities
---

# Regeneration Field Long Projectile

This document details the `regeneration_field_long.xml` entity, which defines a projectile that creates a healing field.

## Core Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: `28` - The radius of the healing field.

### ParticleEmitterComponent (x2)
These components are responsible for emitting visual particles to represent the field.

*   **emitted_material_name**: `spark_green` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles are not affected by gravity.
*   **lifetime_min/max**: `0.5` to `1.5` seconds - Duration of individual particles.
*   **count_min/max**: Varies between the two emitters (2-4 and 4-4) - Number of particles emitted per burst.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **area_circle_radius.max**: `28` - Maximum radius for particle emission.
*   **cosmetic_force_create**: `0` - Particles are not forced to spawn.
*   **emission_interval_min/max_frames**: `1` - Particles are emitted every frame.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **is_emitting**: `1` - The emitter is active.

### Base Component
This entity inherits properties from `data/entities/projectiles/deck/base_field.xml`.

#### SpriteComponent
*   **image_file**: `data/projectiles_gfx/blast_regeneration.xml` - The graphical representation of the projectile's field.

#### LifetimeComponent
*   **lifetime**: `360` seconds - The duration the regeneration field persists.

#### SpriteParticleEmitterComponent
*   **sprite_file**: `data/particles/heal.xml` - Specifies the particle effect for healing.
*   **color**: `1, 1, 1, 1` (White) - The color of the healing particles.

#### ProjectileComponent
This is the primary component defining the projectile's behavior.

*   **damage_game_effect_entities**: `data/entities/misc/effect_regeneration.xml,` - Links to the entity that applies the regeneration effect.
*   **friendly_fire**: `1` - The field can heal allies and the player.
*   **collide_with_shooter_frames**: `0` - The projectile does not collide with the shooter immediately.
*   **damage_by_type**:
    *   **healing**: `-0.05` - The amount of healing applied per tick.
*   **config_explosion**:
    *   **explosion_sprite**: `data/particles/blast_out_regeneration.xml` - The visual effect when the projectile expires.

#### AudioLoopComponent
*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **event_name**: `player_projectiles/field_regeneration/loop` - The name of the looping audio event for the regeneration field.
*   **auto_play**: `1` - The sound starts automatically when the entity is active.