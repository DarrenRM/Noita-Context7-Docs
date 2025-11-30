---
title: Supernova Particle Effect
category: entities
---

# Supernova Particle Effect

This entity defines a powerful visual effect resembling a supernova explosion, primarily composed of "spark" and "spark_white" particles. It's designed to be a cosmetic effect with significant screen shake.

## Key Components

### ProjectileComponent

This component governs the behavior of the entity as a projectile, though in this case, it's primarily used for its explosion and lifetime properties.

*   **`lifetime`**: `5` - The duration the projectile (and its associated effects) will exist.
*   **`damage`**: `0` - This projectile does not deal direct damage.
*   **`die_on_low_velocity`**: `0` - The projectile will not die if its velocity becomes low.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_collision_die`**: `0` - The projectile does not die upon collision.

#### `config_explosion`

This nested element defines the parameters of the explosion that occurs when the projectile's lifetime ends.

*   **`damage`**: `0` - The explosion itself does not deal damage.
*   **`camera_shake`**: `30` - A significant amount of camera shake is applied during the explosion.
*   **`never_cache`**: `1` - Ensures this explosion effect is not cached, allowing for repeated, distinct instances.

### ParticleEmitterComponent (x2)

Two identical `ParticleEmitterComponent` instances are used to generate the visual particles. One emits "spark" and the other "spark\_white" materials.

*   **`emitted_material_name`**: `spark` / `spark_white` - The type of material to emit.
*   **`lifetime_min` / `lifetime_max`**: `3.5` / `4.5` - The lifespan of individual emitted particles.
*   **`count_min` / `count_max`**: `655` / `705` - The number of particles emitted per emission cycle.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.max`**: `12` - The maximum radius of the circular area from which particles are emitted.
*   **`cosmetic_force_create`**: `1` - Forces the creation of cosmetic particles, ensuring they appear even if other conditions aren't met.
*   **`airflow_force`**: `0.5` - The strength of airflow affecting particle movement.
*   **`airflow_time`**: `1.9` - The duration airflow affects particles.
*   **`airflow_scale`**: `0.15` - The scaling factor for airflow.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - Explicitly enables cosmetic particle emission.
*   **`collide_with_grid`**: `0` - Particles do not collide with the game grid.
*   **`render_ultrabright`**: `1` - Particles are rendered with an ultrabright effect.
*   **`x_pos_offset_min` / `x_pos_offset_max`**: `-720` / `720` - The horizontal range for particle emission offsets.
*   **`y_pos_offset_min` / `y_pos_offset_max`**: `-640` / `640` - The vertical range for particle emission offsets.
*   **`x_vel_min` / `x_vel_max`**: `0` / `0` - Particles have no initial horizontal velocity.
*   **`y_vel_min` / `y_vel_max`**: `-180` / `40` - Particles have a downward initial velocity range, with some upward potential.
*   **`is_emitting`**: `1` - The emitter is active.