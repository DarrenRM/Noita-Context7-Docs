---
title: Megalaser Blue Projectile
category: entities
---

# Megalaser Blue Projectile

This document details the configuration of the "Megalaser Blue" projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Core Components

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This section inherits fundamental projectile properties.

*   **`VelocityComponent`**: Defines the projectile's movement characteristics.
    *   `air_friction="0.0"`: No air resistance.
    *   `mass="0.0"`: Zero mass, indicating it's not affected by physics in the traditional sense.
    *   `gravity_y="0.0"`: No gravitational pull.
    *   `terminal_velocity="1"`: A very low terminal velocity, though with no gravity, this is less impactful.

### Projectile Component (`<ProjectileComponent>`)

This is the primary component defining the projectile's behavior and effects.

*   **`speed_min="1"`, `speed_max="1"`**: The projectile travels at a constant speed of 1.
*   **`friction="0.0"`**: No in-flight friction.
*   **`direction_random_rad="0.05"`**: A small amount of randomness in its initial direction.
*   **`lifetime="32"`**: The projectile exists for 32 frames before expiring.
*   **`damage="0"`**: This projectile itself deals no direct damage.
*   **`hit_particle_force_multiplier="5.5"`**: Influences the force of particles spawned on collision.
*   **`camera_shake_when_shot="3.0"`**: Triggers a camera shake when the projectile is fired.
*   **`shoot_light_flash_radius="80"`**: Creates a light flash with a radius of 80 units when fired.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"`**: Specifies the visual effect for the muzzle flash.
*   **`knockback_force="2.5"`**: Applies a knockback force of 2.5 units.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`penetrate_entities="1"`**: The projectile can pass through other entities.
*   **`collide_with_world="0"`**: The projectile does not collide with the environment.

### Lua Component (`<LuaComponent>`)

This component executes a Lua script for custom behavior.

*   **`script_source_file="data/scripts/projectiles/megalaser_blue_spawn.lua"`**: The script responsible for spawning additional effects or logic.
*   **`execute_every_n_frame="30"`**: The script runs every 30 frames.
*   **`remove_after_executed="1"`**: The Lua component is removed after its first execution.

## Visual and Audio Effects

### Sprite Component (`<SpriteComponent>`)

Defines the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/orb_blue_big.xml"`**: Uses a specific sprite for the projectile's visual representation.
*   **`z_index="-1.1"`**: Renders the sprite behind other elements.

### Particle Emitters (`<ParticleEmitterComponent>`)

Multiple emitters contribute to the visual flair of the projectile.

*   **Main Emitter**:
    *   `emitted_material_name="plasma_fading_bright"`: Uses a bright, fading plasma material.
    *   `x_vel_min="-20"`, `x_vel_max="20"`: Moderate horizontal velocity for spawned particles.
    *   `y_vel_min="-30"`, `y_vel_max="10"`: Significant vertical velocity variation.
    *   `velocity_always_away_from_center="1"`: Particles move outwards from the emitter's center.
    *   `count_min="1"`, `count_max="2"`: Spawns a small number of particles.
    *   `lifetime_min="0.3"`, `lifetime_max="0.8"`: Particles have a short lifespan.
*   **Launch Blast A Emitter**:
    *   `delay_frames="30"`: Starts emitting 30 frames after the projectile is created.
    *   `x_vel_min="-20"`, `x_vel_max="800"`: High horizontal velocity for a blast effect.
    *   `y_vel_min="-30"`, `y_vel_max="30"`: Wide vertical velocity range.
    *   `count_min="30"`, `count_max="50"`: Spawns a larger number of particles for a burst.
    *   `lifetime_min="0.1"`, `lifetime_max="0.4"`: Very short-lived particles for a quick blast.
*   **Launch Blast Circle Emitter**:
    *   `delay_frames="29"`: Starts emitting 29 frames after creation.
    *   `x_vel_min="-0"`, `x_vel_max="40"`: Low horizontal velocity.
    *   `y_vel_min="-5"`, `y_vel_max="5"`: Very low vertical velocity.
    *   `area_circle_radius.min="9"`, `area_circle_radius.max="9"`: Emits particles in a tight circle.
    *   `count_min="30"`, `count_max="60"`: Generates a dense ring of particles.
    *   `lifetime_min="0.2"`, `lifetime_max="1.0"`: Particles have a moderate lifespan.
    *   `fade_based_on_lifetime="1"`: Particles fade out as they expire.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   **`radius="100"`**: The light has a radius of 100 units.

### Audio Components (`<AudioComponent>`, `<AudioLoopComponent>`)

Handle the sound effects associated with the projectile.

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    *   `event_root="projectiles/megalaser_blue"`: Sets the root event for this projectile's sounds.
*   **`AudioLoopComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    *   `event_name="projectiles/electric/loop"`: Plays a looping electric sound.
    *   `auto_play="1"`: The loop starts automatically.

### Variable Storage (`<VariableStorageComponent>`)

Stores custom variables.

*   **`name="projectile_file"`**: Stores the path to this projectile's XML file.
    *   `value_string="data/entities/projectiles/megalaser_blue.xml"`: The actual file path.