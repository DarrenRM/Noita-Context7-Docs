---
title: Chain Bolt Projectile
category: entities
---

# Chain Bolt Projectile

This document details the `chain_bolt.xml` entity, which defines the behavior and appearance of the Chain Bolt projectile in Noita. This projectile is designed to chain between entities, dealing damage and leaving a trail of particles.

## Core Components

The Chain Bolt projectile is built upon several core Noita entity components, each contributing to its unique functionality.

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing it to travel in a straight line unless influenced by other forces.

### Projectile Properties (`ProjectileComponent`)

This component governs the projectile's movement, damage, and interaction with the environment.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's lobbing behavior. Values close to 1 suggest a very direct trajectory.
*   **`speed_min="40"`, `speed_max="40"`**: Sets a constant speed for the projectile.
*   **`die_on_low_velocity="0"`**: The projectile will not automatically die if its velocity drops.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with an entity.
*   **`shoot_light_flash_radius="15"`**: The radius of the light flash when the projectile is shot.
*   **`shoot_light_flash_r="250"`, `shoot_light_flash_g="80"`, `shoot_light_flash_b="255"`**: Defines the RGB color of the light flash (a bright purple).
*   **`damage="1.0"`**: The amount of damage the projectile deals.
*   **`lifetime="44"`**: The projectile exists for 44 frames before expiring.
*   **`penetrate_entities="1"`**: The projectile can pass through multiple entities.

### Visual Representation (`SpriteComponent`)

Defines the projectile's visual appearance.

*   **`_enabled="0"`**: This sprite component is disabled by default. The actual sprite is likely handled by the `LuaComponent`.
*   **`image_file="data/projectiles_gfx/slow_bullet.xml"`**: Points to the graphical definition of the projectile's sprite.
*   **`additive="1"`**: The sprite uses additive blending, which can create glowing effects.
*   **`rect_animation="fireball"`**: Specifies a rectangle animation named "fireball" to be used.

### Particle Effects (`ParticleEmitterComponent`)

Generates visual particles associated with the projectile.

*   **`emitted_material_name="spark_purple_bright"`**: The type of particle emitted, a bright purple spark.
*   **`gravity.y="0.0"`**: Particles are not affected by gravity.
*   **`x_vel_min="0"`, `x_vel_max="0"`**: Particles have no horizontal velocity.
*   **`y_vel_min="-2"`, `y_vel_max="2"`**: Particles have a slight vertical velocity range.
*   **`count_min="1"`, `count_max="2"`**: Emits 1 to 2 particles per emission.
*   **`is_trail="1"`**: The particles are emitted as a trail behind the projectile.
*   **`trail_gap="0.5"`**: The spacing between particles in the trail.
*   **`lifetime_min="0.1"`, `lifetime_max="0.8"`**: Particles exist for a short duration.
*   **`emit_real_particles="0"`**: Does not emit actual physics-simulated particles.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`emit_cosmetic_particles="1"`**: Emits particles primarily for visual effect.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="2"`**: Particles are emitted every 1 to 2 frames.
*   **`is_emitting="1"`**: The particle emitter is active.

### Custom Logic (`LuaComponent`)

This component executes custom Lua script for advanced behavior.

*   **`script_source_file="data/scripts/projectiles/chain_bolt.lua"`**: The path to the Lua script that defines the projectile's unique chaining behavior.
*   **`execute_every_n_frame="10"`**: The Lua script is executed every 10 frames.

### State Variables (`VariableStorageComponent`)

Stores persistent data related to the projectile's state.

*   **`name="prev_entity_id"`, `value_int="0"`**: Stores the ID of the previously hit entity.
*   **`name="prev_prev_entity_id"`, `value_int="0"`**: Stores the ID of the entity hit before the previous one. This is likely used to prevent chaining back to the immediate source.
*   **`name="projectile_file"`, `value_string="data/entities/projectiles/deck/chain_bolt.xml"`**: Stores the file path of this projectile entity, useful for the Lua script to reference itself.