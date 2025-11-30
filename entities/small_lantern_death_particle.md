---
title: Small Lantern Death Particle
category: entities
---

# Small Lantern Death Particle

This entity defines the visual effect that occurs when a small lantern dies. It primarily utilizes a `ParticleEmitterComponent` to spawn cosmetic particles.

## Key Components

### ProjectileComponent
This component is present but largely inactive for this particle effect.

*   `lifetime`: `2` - The duration this entity exists.
*   `on_lifetime_out_explode`: `1` - Triggers an explosion when the lifetime ends.
*   `damage`: `0` - Does not deal damage.
*   `on_death_explode`: `0` - Does not explode on death.
*   `on_collision_die`: `0` - Does not die on collision.

### VelocityComponent
Controls the velocity of the entity.

*   `gravity_y`: `0` - No vertical gravity applied to the entity itself.

### ParticleEmitterComponent
This is the core component responsible for generating the visual effect.

*   `emitted_material_name`: `spark` - The material used for the spawned particles.
*   `gravity.y`: `140` - The gravitational pull on the emitted particles.
*   `x_vel_min`, `x_vel_max`: `-40` to `40` - Horizontal velocity range for spawned particles.
*   `y_vel_min`, `y_vel_max`: `-100` to `20` - Vertical velocity range for spawned particles.
*   `count_min`, `count_max`: `8` to `15` - The number of particles spawned per emission.
*   `lifetime_min`, `lifetime_max`: `2.8` to `4.0` - The lifespan of individual spawned particles.
*   `emit_cosmetic_particles`: `1` - Ensures these are cosmetic particles, not affecting gameplay physics.
*   `is_emitting`: `1` - The emitter is active.

## Configuration Details

The `config_explosion` within `ProjectileComponent` is configured to have no effect, as the primary visual is handled by the `ParticleEmitterComponent`.

*   `damage`: `0`
*   `explosion_radius`: `0`
*   `particle_effect`: `0`
*   `sparks_enabled`: `0`