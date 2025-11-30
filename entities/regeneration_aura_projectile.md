---
title: Regeneration Aura Projectile
category: entities
---

# Regeneration Aura Projectile

This entity defines a projectile that creates a healing aura. It's designed to be used in decks and provides a continuous healing effect to entities within its radius.

## Key Components

### GameAreaEffectComponent
This component defines the area of effect for the projectile.

*   **radius**: `32` - The radius of the healing aura in pixels.

### ParticleEmitterComponent (x2)
These components are responsible for emitting visual particles to represent the aura.

*   **emitted_material_name**: `spark_green` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles do not experience vertical gravity.
*   **lifetime_min/max**: `0.5` to `1.5` seconds - The duration each particle exists.
*   **count_min/max**: `2` to `4` - The number of particles emitted per emission.
*   **render_on_grid**: `1` - Particles are rendered on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles fade out as their lifetime ends.
*   **area_circle_radius.max**: `32` - The maximum radius for particle emission.
*   **emission_interval_min/max_frames**: `1` to `1` - Particles are emitted every frame.

### Base (Inherited from `base_field.xml`)
This indicates that the projectile inherits properties from a base field entity.

#### SpriteComponent
*   **image_file**: `data/projectiles_gfx/blast_regeneration.xml` - The graphical representation of the projectile's effect.

#### LifetimeComponent
*   **lifetime**: `140` - The duration the aura persists in frames.

#### ProjectileComponent
This is the core component defining the projectile's behavior.

*   **damage_game_effect_entities**: `data/entities/misc/effect_regeneration.xml,` - Links to an entity that applies the regeneration effect.
*   **friendly_fire**: `1` - The aura affects both enemies and allies.
*   **collide_with_shooter_frames**: `0` - The projectile does not collide with the shooter immediately.
*   **damage_by_type**:
    *   **healing**: `-0.05` - The amount of healing applied per tick. The negative value signifies healing.
*   **config_explosion**:
    *   **explosion_sprite**: `data/particles/blast_out_regeneration.xml` - The visual effect when the projectile expires.

#### AudioLoopComponent
*   **file**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **event_name**: `player_projectiles/field_regeneration/loop` - The specific audio event for the regeneration aura loop.
*   **auto_play**: `1` - The sound starts playing automatically.