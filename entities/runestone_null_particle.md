---
title: Runestone Null Particle
category: entities
---

# Runestone Null Particle

This entity defines a particle effect associated with the "Runestone Null". It primarily consists of a projectile component that doesn't interact physically or deal damage, and a particle emitter that generates purple sparks.

## ProjectileComponent

This component defines the projectile's behavior. For the Runestone Null, it's configured to be inactive in terms of damage and collision.

### Key Attributes:

*   **`speed_min`**: `0` - Minimum projectile speed.
*   **`speed_max`**: `0` - Maximum projectile speed.
*   **`die_on_low_velocity`**: `0` - Projectile does not die when its velocity is low.
*   **`on_death_explode`**: `0` - Projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `0` - No graphics are left behind when the projectile dies.
*   **`on_lifetime_out_explode`**: `0` - Projectile does not explode when its lifetime ends.
*   **`on_collision_die`**: `0` - Projectile does not die upon collision.
*   **`damage`**: `0` - Projectile deals no damage.
*   **`lifetime`**: `2` - The projectile exists for 2 seconds.

#### `config_explosion` (Nested within `ProjectileComponent`)

This sub-component defines explosion properties, which are all disabled for this projectile.

*   **`damage`**: `0`
*   **`camera_shake`**: `0`
*   **`explosion_radius`**: `0`
*   **`particle_effect`**: `0`
*   **`damage_mortals`**: `0`
*   **`physics_explosion_power.max`**: `0`
*   **`physics_throw_enabled`**: `0`

## ParticleEmitterComponent

This component is responsible for generating visual particles. In this case, it creates purple sparks.

### Key Attributes:

*   **`emitted_material_name`**: `"spark_purple_bright"` - The material of the particles to be emitted.
*   **`gravity.y`**: `50.0` - The gravitational pull on the particles in the Y-axis.
*   **`lifetime_min`**: `1.5` - Minimum lifetime of emitted particles in seconds.
*   **`lifetime_max`**: `2.5` - Maximum lifetime of emitted particles in seconds.
*   **`count_min`**: `25` - Minimum number of particles emitted per emission interval.
*   **`count_max`**: `35` - Maximum number of particles emitted per emission interval.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: `8` - The maximum radius of the circular area from which particles are emitted.
*   **`airflow_force`**: `0.5` - The force applied by airflow.
*   **`airflow_time`**: `1.9` - The duration airflow affects particles.
*   **`airflow_scale`**: `0.15` - The scale of the airflow effect.
*   **`emission_interval_min_frames`**: `1` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `1` - Maximum frames between particle emissions.
*   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.
*   **`x_vel_min`**: `-40` - Minimum initial velocity in the X-axis.
*   **`x_vel_max`**: `40` - Maximum initial velocity in the X-axis.
*   **`y_vel_min`**: `-40` - Minimum initial velocity in the Y-axis.
*   **`y_vel_max`**: `40` - Maximum initial velocity in the Y-axis.
*   **`is_emitting`**: `1` - The particle emitter is active.