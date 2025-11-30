---
title: Levitation Trail Projectile
category: entities
---

---

# Levitation Trail Projectile

This entity defines a projectile that creates a levitation trail effect. It's primarily used for visual feedback and has minimal impact on gameplay mechanics.

## Key Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `mass="0.04"`: A small mass value.
    *   `air_friction="2"`: Moderate air resistance.
    *   `terminal_velocity="2000"`: A high terminal velocity, though not heavily utilized due to other settings.

### Projectile (`<ProjectileComponent>`)

This component governs the projectile's behavior and interactions.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Defines a very slight lobbing behavior, almost straight.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed.
*   **`direction_random_rad="0"`**: No random deviation in direction.
*   **`collide_with_world="1"`**: The projectile can collide with the environment.
*   **`penetrate_world="1"`**: The projectile can pass through the world geometry.
*   **`penetrate_world_velocity_coeff="0.3"`**: A coefficient affecting penetration based on velocity (less relevant here due to zero initial speed).
*   **`on_death_explode="0"`**: Does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: Does not leave a sprite upon death.
*   **`on_lifetime_out_explode="0"`**: Does not explode when its lifetime ends.
*   **`on_collision_die="1"`**: The projectile dies upon collision.
*   **`die_on_liquid_collision="0"`**: Does not die upon colliding with liquids.
*   **`lifetime="300"`**: The projectile exists for 300 frames.
*   **`damage="0.12"`**: Deals a very small amount of damage.
*   **`ragdoll_fx_on_collision="BLOOD_SPRAY"`**: Spawns a blood spray effect on collision.
*   **`bounces_left="0"`**: Does not bounce.
*   **`shoot_light_flash_radius="1"`**: Creates a small light flash when shot.
*   **`knockback_force="0"`**: No knockback effect.

### Light (`<LightComponent>`)

Adds a subtle light source to the projectile.

*   **`radius="20"`**: The light radius.
*   **`r="20"`, `g="70"`, `b="20"`**: A greenish color for the light.

### Particle Emitters (`<ParticleEmitterComponent>`)

Two particle emitters are used to create the visual trail effect.

#### Emitter 1 (Cloud Effect)

*   **`emitted_material_name="plasma_fading_green"`**: The material used for the emitted particles.
*   **`emitter_lifetime_frames="280"`**: The emitter lasts for 280 frames.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`x_vel_min="-20"`, `x_vel_max="20"`**: Particles have a horizontal velocity range.
*   **`y_vel_min="-20"`, `y_vel_max="20"`**: Particles have a vertical velocity range.
*   **`friction="10"`**: Particles experience friction.
*   **`count_min="1"`, `count_max="1"`**: Emits one particle per emission.
*   **`lifetime_min="0.05"`, `lifetime_max="0.8"`**: Particle lifetime varies.
*   **`emit_real_particles="0"`**: Emits cosmetic particles.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`emit_cosmetic_particles="1"`**: Explicitly emits cosmetic particles.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="16"`**: Emission interval varies.

#### Emitter 2 (Trail Effect)

*   **`emitted_material_name="plasma_fading_green"`**: The material used for the emitted particles.
*   **`emitter_lifetime_frames="280"`**: The emitter lasts for 280 frames.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`x_vel_min="0"`, `x_vel_max="0"`**: Particles have no horizontal velocity.
*   **`y_vel_min="0"`, `y_vel_max="0"`**: Particles have no vertical velocity.
*   **`friction="10"`**: Particles experience friction.
*   **`count_min="1"`, `count_max="1"`**: Emits one particle per emission.
*   **`lifetime_min="0.05"`, `lifetime_max="0.05"`**: Particles have a very short, fixed lifetime.
*   **`emit_real_particles="0"`**: Emits cosmetic particles.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`is_trail="1"`**: This emitter is specifically configured as a trail.
*   **`trail_gap="1"`**: The gap between trail particles.
*   **`emit_cosmetic_particles="1"`**: Explicitly emits cosmetic particles.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Emits particles at a very high rate.