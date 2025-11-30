---
title: Megalaser Projectile
category: entities
---

# Megalaser Projectile

This document details the configuration of the "Megalaser" projectile entity in Noita, focusing on its core attributes and effects relevant to AI-assisted modding.

## Core Components

The Megalaser projectile is defined by several key components that dictate its behavior, appearance, and interaction within the game.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `air_friction="0.0"`: No air resistance.
    *   `mass="0.0"`: Zero mass, indicating it's not affected by physics in the traditional sense.
    *   `gravity_y="0.0"`: No gravitational pull.
    *   `terminal_velocity="1"`: A very low terminal velocity, effectively meaning it travels at a constant speed.

### Projectile Behavior (`ProjectileComponent`)

This is the primary component defining the projectile's unique characteristics.

*   **`speed_min="1"`, `speed_max="1"`**: The projectile travels at a fixed speed of 1.
*   **`friction="0.0"`**: No in-flight friction.
*   **`direction_random_rad="0.05"`**: A small amount of randomness in its initial direction.
*   **`lifetime="32"`**: The projectile exists for 32 frames before expiring.
*   **`damage="5"`**: Deals 5 damage on impact.
*   **`camera_shake_when_shot="3.0"`**: Triggers a camera shake of magnitude 3.0 when fired.
*   **`shoot_light_flash_radius="80"`**: Creates a light flash with a radius of 80 when shot.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_launcher.xml"`**: Specifies the visual effect for the muzzle flash.
*   **`knockback_force="2.5"`**: Applies a knockback force of 2.5 to targets.
*   **`collide_with_world="0"`**: The projectile does not collide with the environment.
*   **`penetrate_entities="0"`**: The projectile does not penetrate other entities.

### Lua Scripting (`LuaComponent`)

Two Lua scripts are attached to manage the projectile's lifecycle and effects.

*   **`megalaser_init.lua`**:
    *   `script_source_file="data/scripts/projectiles/megalaser_init.lua"`
    *   `execute_on_added="1"`: Runs once when the projectile is spawned.
    *   `remove_after_executed="1"`: The script component is removed after execution.
*   **`megalaser_launch.lua`**:
    *   `script_source_file="data/scripts/projectiles/megalaser_launch.lua"`
    *   `execute_every_n_frame="30"`: Runs every 30 frames.
    *   `remove_after_executed="1"`: The script component is removed after execution.

## Visual Effects (`ParticleEmitterComponent`)

The Megalaser projectile utilizes several particle emitters to create its visual flair.

### Image Emitter

*   **`emitted_material_name="plasma_fading_green"`**: Uses a fading green plasma material.
*   **`offset.x="-27"`**: Positioned slightly to the left of the projectile's origin.
*   **`lifetime_min="0.5"`, `lifetime_max="2"`**: Particles last between 0.5 and 2 frames.
*   **`count_min="1"`, `count_max="1"`**: Emits a single particle at a time.
*   **`image_animation_file="data/particles/image_emitters/wand_64.png"`**: Uses a specific animation file for particle appearance.
*   **`is_emitting="1"`**: The emitter is active.

### Launch Blast A

*   **`emitted_material_name="plasma_fading_green"`**: Uses a fading green plasma material.
*   **`delay_frames="30"`**: Starts emitting 30 frames after the projectile is spawned.
*   **`x_vel_min="-20"`, `x_vel_max="800"`**: Wide range of horizontal velocity for particles.
*   **`y_vel_min="-30"`, `y_vel_max="30"`**: Vertical velocity range.
*   **`velocity_always_away_from_center="1"`**: Particles are always propelled away from the center.
*   **`area_circle_radius.min="10"`, `area_circle_radius.max="10"`**: Particles are emitted within a 10-unit radius circle.
*   **`count_min="30"`, `count_max="50"`**: Emits between 30 and 50 particles per emission.
*   **`lifetime_min="0.1"`, `lifetime_max="0.4"`**: Short particle lifespan.
*   **`emitter_lifetime_frames="3"`**: The emitter itself lasts for 3 frames.
*   **`emit_real_particles="0"`**: Emits cosmetic particles.

### Launch Blast Circle

*   **`emitted_material_name="plasma_fading_green"`**: Uses a fading green plasma material.
*   **`delay_frames="29"`**: Starts emitting 29 frames after the projectile is spawned.
*   **`x_vel_min="0"`, `x_vel_max="40"`**: Limited horizontal velocity.
*   **`y_vel_min="-5"`, `y_vel_max="5"`**: Small vertical velocity range.
*   **`velocity_always_away_from_center="1"`**: Particles are always propelled away from the center.
*   **`area_circle_radius.min="9"`, `area_circle_radius.max="9"`**: Particles are emitted within a 9-unit radius circle.
*   **`count_min="30"`, `count_max="60"`**: Emits between 30 and 60 particles per emission.
*   **`lifetime_min="0.2"`, `lifetime_max="1.0"`**: Particles last between 0.2 and 1.0 frames.
*   **`emitter_lifetime_frames="2"`**: The emitter itself lasts for 2 frames.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime decreases.

## Lighting (`LightComponent`)

*   **`radius="100"`**: The projectile emits light with a radius of 100 units.

## Audio (`AudioComponent`)

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank file.
*   **`event_root="player_projectiles/megalaser"`**: Defines the root event for Megalaser projectile sounds.