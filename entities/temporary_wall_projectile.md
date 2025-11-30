---
title: Temporary Wall Projectile
category: entities
---

# Temporary Wall Projectile

This entity defines a projectile that creates a temporary, static wall upon impact. It's designed to be a defensive or obstruction tool rather than an offensive one.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits physics properties from a base item, enabling physical interaction and collision.

### Physics Components

*   **`PhysicsBody2Component`**:
    *   `kill_entity_after_initialized="0"`: The entity persists after its initial setup.
    *   `is_static="1"`: The wall remains stationary once created.
    *   `fixed_rotation="1"`: The wall does not rotate.
    *   `destroy_body_if_entity_destroyed="1"`: The physics body is removed if the entity is destroyed.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/temporary_wall.png"`: Specifies the visual sprite for the wall.
    *   `material="rock_box2d_hard"`: Defines the physical material properties, influencing interactions.

### Velocity Component

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity while in flight.
    *   `air_friction="10"`: High air friction to quickly reduce any residual velocity.
    *   `mass="0.00"`: Negligible mass, indicating it's not intended for forceful impact.

### Projectile Component

*   **`ProjectileComponent`**:
    *   `_enabled="1"`: The projectile functionality is active.
    *   `speed_min="0"`, `speed_max="0"`: The projectile has no initial speed, implying it's spawned at its destination or has zero velocity.
    *   `die_on_low_velocity="0"`: The projectile does not disappear due to low speed.
    *   `on_death_explode="0"`: No explosion occurs when the projectile dies.
    *   `on_lifetime_out_explode="0"`: No explosion occurs when its lifetime expires.
    *   `damage="0"`: The projectile deals no damage.
    *   `on_collision_die="0"`: The projectile does not die upon collision.
    *   `lifetime="300"`: The projectile exists for 300 frames before expiring.
    *   `knockback_force="0"`: No knockback is applied.
    *   `damage_every_x_frames="25"`: Damage is not relevant as damage is 0.
    *   **`config_explosion`**: All explosion-related parameters are disabled (`never_cache`, `camera_shake`, `explosion_radius`, `hole_enabled`, `particle_effect`, `damage_mortals`, `physics_throw_enabled`, `sparks_enabled`, `stains_enabled`) as this projectile is not meant to explode or cause environmental damage.

### Particle Emitter Component

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_purple_bright"`: Spawns purple sparks.
    *   `lifetime_min="1.0"`, `lifetime_max="3.0"`: Particles last between 1 and 3 seconds.
    *   `count_min="4"`, `count_max="4"`: Emits a fixed number of particles.
    *   `cosmetic_force_create="1"`: Particles are purely cosmetic.
    *   `airflow_force="0.151"`, `airflow_time="1.01"`, `airflow_scale="0.05"`: Subtle airflow applied to particles.
    *   `emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`: Particles are emitted continuously.
    *   `image_animation_file="data/particles/image_emitters/temporary_wall.png"`: Uses a specific animation for emitted particles.
    *   `x_vel_min="0"`, `x_vel_max="0"`: No horizontal velocity for particles.
    *   `y_vel_min="-20"`, `y_vel_max="20"`: Particles are emitted with vertical velocity.

### Audio Loop Component

*   **`AudioLoopComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    *   `event_name="player_projectiles/wall/loop_solid"`: Triggers a specific sound event for solid walls.
    *   `auto_play="1"`: The sound starts automatically.