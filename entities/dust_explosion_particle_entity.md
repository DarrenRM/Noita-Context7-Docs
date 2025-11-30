---
title: Dust Explosion Particle Entity
category: entities
---

# Dust Explosion Particle Entity

This entity defines the visual and behavioral aspects of a dust explosion effect in Noita. It primarily uses particle emitters to create a visual representation of dust and sparks.

## Key Components

### ProjectileComponent

This component defines the projectile-like behavior of the entity. In this case, it's configured to primarily act as a timed explosion rather than a projectile with physical interaction.

*   **`lifetime`**: `10` - The entity will exist for 10 frames before its `on_lifetime_out_explode` triggers.
*   **`on_lifetime_out_explode`**: `1` - When the lifetime expires, the entity will explode.
*   **`damage`**: `0` - The explosion itself deals no damage.
*   **`on_death_explode`**: `0` - The entity does not explode upon dying from other conditions (like low velocity).
*   **`on_collision_die`**: `0` - The entity does not die upon collision.

#### `config_explosion`

This nested configuration defines the parameters of the explosion triggered by `on_lifetime_out_explode`.

*   **`sparks_enabled`**: `1` - Sparks will be generated during the explosion.
*   **`spark_material`**: `"rock_static"` - The material used for the generated sparks.
*   **`sparks_min`**: `10` - Minimum number of sparks to create.
*   **`sparks_max`**: `30` - Maximum number of sparks to create.
*   **`damage`**: `0` - The explosion deals no damage.
*   **`camera_shake`**: `0` - No camera shake is applied.
*   **`explosion_radius`**: `0` - The explosion has no radius for damage or effect propagation.
*   **`physics_explosion_power.max`**: `0` - No physics-based force is applied.

### VelocityComponent

This is a placeholder component and does not have any specific configurable attributes that significantly impact this entity's behavior.

### ParticleEmitterComponent (Dust)

This component is responsible for emitting the primary dust particles.

*   **`emitted_material_name`**: `"silver"` - The material used for the dust particles.
*   **`lifetime_min`**: `5.5` - Minimum lifetime of emitted dust particles in frames.
*   **`lifetime_max`**: `15.5` - Maximum lifetime of emitted dust particles in frames.
*   **`count_min`**: `5` - Minimum number of particles emitted per emission interval.
*   **`count_max`**: `15` - Maximum number of particles emitted per emission interval.
*   **`area_circle_radius.max`**: `16` - The maximum radius of the circle from which particles are emitted.
*   **`airflow_force`**: `0.5` - A force applied to particles, simulating airflow.
*   **`airflow_time`**: `1.9` - Duration of the airflow effect.
*   **`x_vel_min`**: `-20` - Minimum horizontal velocity for emitted particles.
*   **`x_vel_max`**: `20` - Maximum horizontal velocity for emitted particles.
*   **`y_vel_min`**: `-20` - Minimum vertical velocity for emitted particles.
*   **`y_vel_max`**: `20` - Maximum vertical velocity for emitted particles.
*   **`fade_based_on_lifetime`**: `1` - Particles will fade out as their lifetime decreases.

### ParticleEmitterComponent (Sparks)

This component emits secondary "spark" particles, likely for a more dynamic visual effect.

*   **`emitted_material_name`**: `"spark_white"` - The material used for these spark particles.
*   **`gravity.y`**: `200.0` - Applies significant downward gravity to the sparks.
*   **`count_min`**: `15` - Minimum number of sparks emitted per emission interval.
*   **`count_max`**: `25` - Maximum number of sparks emitted per emission interval.
*   **`lifetime_min`**: `100` - Minimum lifetime of emitted spark particles in frames.
*   **`lifetime_max`**: `150` - Maximum lifetime of emitted spark particles in frames.
*   **`x_vel_min`**: `-20` - Minimum horizontal velocity for emitted sparks.
*   **`x_vel_max`**: `20` - Maximum horizontal velocity for emitted sparks.
*   **`y_vel_min`**: `-40` - Minimum vertical velocity for emitted sparks.
*   **`x_pos_offset_min`**: `-5` - Minimum horizontal offset from the emitter's origin.
*   **`x_pos_offset_max`**: `5` - Maximum horizontal offset from the emitter's origin.
*   **`y_pos_offset_min`**: `-12` - Minimum vertical offset from the emitter's origin.
*   **`y_pos_offset_max`**: `2` - Maximum vertical offset from the emitter's origin.