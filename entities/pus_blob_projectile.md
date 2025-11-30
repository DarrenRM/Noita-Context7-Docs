---
title: Pus Blob Projectile
category: entities
---

# Pus Blob Projectile

This document details the configuration for the "Pus Blob" projectile entity in Noita, focusing on its behavior, visual effects, and damage properties.

## Core Entity Configuration

The `Entity` tag defines the base object.

*   **`tags="hittable"`**: This projectile can be hit by other entities.
*   **`name="$projectile_default"`**: Inherits default projectile properties.

## Base Projectile Properties

The `Base` component inherits common projectile behaviors.

### `Base/VelocityComponent`

Controls the physical movement of the projectile.

*   **`gravity_y="10"`**: Applies a downward gravitational force.
*   **`air_friction="0"`**: No air resistance.
*   **`mass="0.055"`**: The projectile's mass.

## Projectile Behavior (`ProjectileComponent`)

This component defines the specific actions and characteristics of the pus blob.

*   **`speed_min="90"` / `speed_max="115"`**: The range of initial projectile speeds.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`on_collision_die="1"`**: The projectile is destroyed upon colliding with something.
*   **`die_on_low_velocity="1"`**: The projectile is destroyed if its speed drops too low.
*   **`damage="0.35"`**: The base damage dealt by the projectile itself.
*   **`lifetime="130"`**: The duration in frames before the projectile expires.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: RGB values for the light flash when the projectile is fired.
*   **`shoot_light_flash_radius`**: The radius of the light flash.
*   **`knockback_force="1.5"`**: The force applied to entities that are hit.

### `ProjectileComponent/config_explosion`

Defines the properties of the explosion that occurs when the projectile dies.

*   **`never_cache="1"`**: Prevents the explosion from being cached, ensuring it's always generated fresh.
*   **`damage="0.4"`**: Damage dealt by the explosion.
*   **`camera_shake="3.5"`**: Intensity of camera shake upon explosion.
*   **`explosion_radius="14"`**: The area of effect for the explosion.
*   **`explosion_sprite="data/particles/smoke_cloud_red_1.xml"`**: The visual sprite used for the explosion effect.
*   **`create_cell_probability="90"`**: High chance to create new cells upon explosion.
*   **`create_cell_material="pus"`**: The material of the cells created.
*   **`hole_enabled="1"`**: Creates a hole in the terrain upon explosion.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the explosion hole.
*   **`damage_mortals="1"`**: The explosion damages living entities.
*   **`physics_explosion_power.min="0.2"` / `physics_explosion_power.max="0.3"`**: Controls the physics force applied to objects by the explosion.
*   **`shake_vegetation="1"`**: Causes nearby vegetation to shake.
*   **`stains_enabled="1"`**: Creates stains on surfaces.
*   **`stains_radius="9"`**: The radius of the stains.

## Particle Effects (`ParticleEmitterComponent`)

This component manages the visual particles emitted by the projectile.

*   **`emitted_material_name="poison_gas"`**: The material of the emitted particles.
*   **`count_min="1"` / `count_max="2"` (and `count_min="1"` / `count_max="3"`)**: The number of particles emitted per emission.
*   **`gravity.y="0"`**: Particles are not affected by gravity.
*   **`x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`**: The velocity range of emitted particles.
*   **`is_trail="1"`**: The particles form a trail behind the projectile.
*   **`trail_gap="2.5"`**: The spacing between trail particles.
*   **`lifetime_min="0.1"` / `lifetime_max="1.3"`**: The lifespan of individual particles.
*   **`fade_based_on_lifetime="1"`**: Particles fade out as their lifetime ends.
*   **`emit_cosmetic_particles="1"`**: Emits particles that are purely visual.

## Lighting (`LightComponent`)

Adds a light source to the projectile.

*   **`radius="30"`**: The radius of the light.
*   **`r="99"`, `g="205"`, `b="189"`**: RGB values for the light color (a greenish-cyan).

## Audio (`AudioComponent`)

Defines the sound effects associated with the projectile.

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound.
*   **`event_root="projectiles/slime_gas"`**: The specific sound event to play.

## Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/projectiles/pusblob.xml"`**: The value, referencing its own file path.