---
title: Slime Trail Projectile
category: entities
---

# Slime Trail Projectile

This document describes the `slimetrail.xml` entity, which defines a projectile that leaves a trail of slime particles.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="50"`: Applies a downward gravitational force.
    *   `mass="0.06"`: Defines the projectile's mass.

### Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior and characteristics.

*   **`_enabled="1"`**: Enables the component.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the projectile's lobbing behavior, influencing its arc.
*   **`speed_min="260"`, `speed_max="270"`**: Sets the initial speed range of the projectile.
*   **`die_on_low_velocity="1"`**: The projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No sprite is left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur, it would not damage the shooter.
*   **`damage="0"`**: This projectile deals no direct damage.
*   **`on_collision_die="1"`**: The projectile is destroyed upon colliding with something.
*   **`lifetime="120"`**: The projectile exists for 120 frames.
*   **`shoot_light_flash_r="255"`, `shoot_light_flash_g="140"`, `shoot_light_flash_b="10"`**: Defines the RGB color of a light flash when the projectile is shot (orange-ish).
*   **`shoot_light_flash_radius="150"`**: The radius of the light flash.
*   **`collide_with_entities="0"`**: The projectile does not collide with other entities.
*   **`knockback_force="1.6"`**: Applies a knockback force of 1.6 units.

### Sprite Component (`SpriteComponent`)

Defines the visual representation of the projectile.

*   **`_enabled="1"`**: Enables the component.
*   **`alpha="1"`**: The sprite is fully opaque.
*   **`image_file="data/particles/blob.xml"`**: Uses a "blob" particle graphic.
*   **`offset_x="0"`, `offset_y="0"`**: No offset from the projectile's origin.
*   **`update_transform_rotation="0"`**: The sprite's rotation does not update with the projectile's transform.

### Particle Emitter Component (`ParticleEmitterComponent`)

Responsible for generating the slime trail effect.

*   **`emitted_material_name="slime_green"`**: The material of the particles emitted is "slime\_green".
*   **`offset.x="0"`, `offset.y="0"`**: Particles are emitted from the projectile's origin.
*   **`x_pos_offset_min="-1"`, `y_pos_offset_min="-3"`, `x_pos_offset_max="1"`, `y_pos_offset_max="3"`**: Small random offsets for particle spawn position.
*   **`x_vel_min="-10"`, `x_vel_max="10"`, `y_vel_min="-10"`, `y_vel_max="10"`**: Small random velocity applied to emitted particles.
*   **`count_min="1"`, `count_max="3"`**: Emits 1 to 3 particles per emission.
*   **`lifetime_min="0.3"`, `lifetime_max="0.6"`**: Particles live for 0.3 to 0.6 seconds.
*   **`is_trail="1"`**: This emitter is configured to create a trail effect.
*   **`trail_gap="0.2"`**: The gap between emitted particles in the trail.
*   **`render_on_grid="1"`**: Particles are rendered on the game grid.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime decreases.
*   **`create_real_particles="0"`**: Does not create "real" particles that interact with physics.
*   **`emit_cosmetic_particles="1"`**: Emits cosmetic particles for visual effect.
*   **`emission_interval_min_frames="1"`, `emission_interval_max_frames="1"`**: Particles are emitted every frame.
*   **`is_emitting="1"`**: The emitter is active.

### Light Component (`LightComponent`)

Adds a light source to the projectile.

*   **`_enabled="1"`**: Enables the component.
*   **`radius="120"`**: The radius of the light.
*   **`r="150"`, `g="180"`, `b="20"`**: Defines the light color (a yellowish-green).

### Lua Component (`LuaComponent`)

Attaches a Lua script for custom logic.

*   **`_enabled="1"`**: Enables the component.
*   **`script_source_file="data/scripts/projectiles/slimetrail.lua"`**: Specifies the Lua script to execute.
*   **`execute_every_n_frame="2"`**: The script runs every 2 frames.

### Variable Storage Component (`VariableStorageComponent`)

Stores custom variables.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/slimetrail.xml"`**: Stores the path to this entity's XML file.