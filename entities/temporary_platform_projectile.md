---
title: Temporary Platform Projectile
category: entities
---

# Temporary Platform Projectile

This entity defines a projectile that creates a temporary, static platform upon impact. It's designed to be a utility projectile rather than a damaging one.

## Key Components

### Base Entity and Physics

*   **`Base file="data/entities/base_item_physics2.xml"`**: Inherits fundamental physics properties.
*   **`PhysicsBody2Component`**:
    *   `is_static="1"`: The platform itself will be static once created.
    *   `kill_entity_after_initialized="0"`: The projectile entity persists after initialization to create the platform.
    *   `destroy_body_if_entity_destroyed="1"`: The physics body is removed if the entity is destroyed.
*   **`PhysicsImageShapeComponent`**:
    *   `image_file="data/props_gfx/temporary_platform.png"`: Specifies the visual appearance of the platform.
    *   `material="rock_box2d_hard"`: Defines the physical material properties.

### Velocity Component

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile itself is not affected by gravity.
    *   `air_friction="10"`: Some air friction is applied.
    *   `mass="0.00"`: The projectile has negligible mass.

### Projectile Component

*   **`ProjectileComponent`**:
    *   `lifetime="300"`: The platform persists for 300 frames (5 seconds).
    *   `damage="0"`: The projectile deals no damage.
    *   `on_collision_die="0"`: The projectile does not die upon collision.
    *   `die_on_low_velocity="0"`: The projectile does not die due to low velocity.
    *   `on_death_explode="0"`: No explosion occurs when the projectile "dies" (e.g., lifetime ends).
    *   `explosion_dont_damage_shooter="1"`: If an explosion were to occur, it wouldn't damage the shooter.
    *   `knockback_force="0"`: No knockback is applied.
    *   `damage_every_x_frames="25"`: This is set but irrelevant as damage is 0.
    *   **`config_explosion`**: Configured to have no effect (e.g., `explosion_radius="0"`, `damage_mortals="0"`, `hole_enabled="0"`).

### Particle Emitter Component

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name="spark_purple_bright"`: Spawns purple sparks.
    *   `lifetime_min="1.0"`, `lifetime_max="3.0"`: Sparks last between 1 and 3 seconds.
    *   `count_min="4"`, `count_max="4"`: Emits a fixed number of sparks.
    *   `cosmetic_force_create="1"`: Ensures particles are created.
    *   `image_animation_file="data/particles/image_emitters/temporary_platform.png"`: Uses a specific animation for the emitted particles.
    *   `x_vel_min="-20"`, `x_vel_max="20"`: Sparks have horizontal velocity.
    *   `y_vel_min="0"`, `y_vel_max="0"`: Sparks have no initial vertical velocity.

### Audio Components

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: Uses the projectiles audio bank.
    *   `event_root="player_projectiles/wall"`: Sets the audio event root for projectile sounds.
*   **`AudioLoopComponent`**:
    *   `event_name="player_projectiles/wall/loop_solid"`: Plays a looping sound associated with solid projectiles.
    *   `auto_play="1"`: The sound starts automatically.