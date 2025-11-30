---
title: Keyshot Projectile
category: entities
---

# Keyshot Projectile

This document details the `keyshot.xml` entity, defining a player projectile in Noita.

## Core Attributes

The `keyshot.xml` entity is a projectile with several key attributes that define its behavior and impact.

### Base Projectile Configuration

*   **`gravity_y`**: `10` - Controls the vertical acceleration due to gravity.
*   **`air_friction`**: `0` - Indicates no air resistance.
*   **`mass`**: `0.04` - The projectile's mass.

### Projectile Component

This component governs the projectile's flight, damage, and death effects.

*   **`speed_min`**: `180` - The minimum initial velocity of the projectile.
*   **`speed_max`**: `205` - The maximum initial velocity of the projectile.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`die_on_low_velocity`**: `1` - The projectile dies if its velocity drops too low.
*   **`damage`**: `3` - The base damage dealt by the projectile.
*   **`lifetime`**: `330` - The duration in frames before the projectile expires.
*   **`shoot_light_flash_radius`**: `170` - The radius of the light flash when the projectile is fired.
*   **`shoot_light_flash_r`, `shoot_light_flash_g`, `shoot_light_flash_b`**: `255` (all) - Sets the light flash to white.

### Explosion Configuration (`config_explosion`)

Defines the effects when the projectile explodes.

*   **`damage`**: `4` - Damage dealt by the explosion.
*   **`camera_shake`**: `10.5` - Intensity of camera shake upon explosion.
*   **`explosion_radius`**: `80` - The radius of the explosion.
*   **`create_cell_material`**: `magic_liquid` - The material created by the explosion.
*   **`create_cell_probability`**: `90` - The percentage chance to create the specified material.
*   **`hole_destroy_liquid`**: `1` - The explosion destroys liquids.
*   **`ray_energy`**: `1000000` - High energy for ray interactions.
*   **`hole_enabled`**: `1` - The explosion creates holes.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`physics_explosion_power.min`**: `2.0` - Minimum physics force applied by the explosion.
*   **`physics_explosion_power.max`**: `3.2` - Maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Objects are thrown by the explosion.
*   **`shake_vegetation`**: `1` - Vegetation is shaken by the explosion.
*   **`stains_enabled`**: `1` - Explosion stains are created.
*   **`stains_radius`**: `9` - The radius of the stains.

### Sprite Component

Defines the visual representation of the projectile.

*   **`image_file`**: `""` - No specific sprite file is defined here, likely relying on default or inherited sprites.
*   **`offset_x`**, **`offset_y`**: `4.5` - Offsets for the sprite's position.
*   **`update_transform_rotation`**: `0` - The sprite does not update its rotation based on the projectile's transform.

### Particle Emitters

Two particle emitters are used to create visual effects.

#### `ParticleEmitterComponent`

*   **`emitted_material_name`**: `magic_liquid` - The material of the emitted particles.
*   **`count_min`**, **`count_max`**: `1` to `2` - Number of particles emitted per burst.
*   **`lifetime_min`**, **`lifetime_max`**: `0.1` to `0.3` - Duration of emitted particles.
*   **`create_real_particles`**: `1` - Creates actual game particles.
*   **`emit_cosmetic_particles`**: `0` - Does not emit cosmetic particles.
*   **`is_emitting`**: `1` - The emitter is active.

#### `SpriteParticleEmitterComponent`

*   **`sprite_file`**: `data/particles/gatesymbol_$[1-8].png` - Uses a sequence of gate symbol sprites.
*   **`lifetime`**: `1.5` - Duration of these sprite particles.
*   **`color_change.a`**: `-0.8` - The alpha value decreases over time, causing fading.
*   **`velocity_always_away_from_center`**: `1` - Particles move away from their emission point.
*   **`emission_interval_min_frames`**, **`emission_interval_max_frames`**: `5` - Controls the timing of particle emissions.
*   **`count_min`**, **`count_max`**: `1` - Emits one particle per burst.

### Variable Storage Component

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/keyshot.xml` - Stores the path to this entity's file.