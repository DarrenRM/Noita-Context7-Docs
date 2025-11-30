---
title: Healshot Projectile
category: entities
---

# Healshot Projectile

This document details the `healshot.xml` entity, which defines a projectile in Noita designed for healing.

## Core Functionality

The `healshot.xml` entity represents a projectile with the primary function of healing targets. It inherits base projectile properties and adds specific behaviors for its healing effect.

### Key Attributes

*   **`friendly_fire="1"`**: Allows the projectile to affect friendly entities (i.e., heal them).
*   **`damage="0"`**: The projectile itself deals no damage.
*   **`healing="-0.2"`**: Within the `damage_by_type` tag, this specifies that the projectile *heals* by a value of 0.2. The negative sign indicates healing.
*   **`lifetime="50"`**: The projectile exists for 50 frames before expiring.
*   **`on_death_explode="1"`**: The projectile will explode upon death (e.g., after its lifetime expires or on collision).
*   **`on_collision_die="1"`**: The projectile will die upon colliding with an entity.
*   **`explosion_dont_damage_shooter="1"`**: If the projectile explodes, it will not damage the entity that fired it.
*   **`muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml"`**: Specifies the visual effect for the muzzle flash when this projectile is fired.

## Projectile Behavior

### Velocity and Movement

*   **`gravity_y="0"`**: The projectile is not affected by gravity.
*   **`air_friction="-2.0"`**: Applies a negative air friction, which can influence its movement dynamics.
*   **`mass="0.04"`**: Defines the projectile's mass.
*   **`speed_min="200"`**, **`speed_max="250"`**: The projectile's speed will be randomized between these values.
*   **`lob_min="0.8"`**, **`lob_max="1.1"`**: Controls the lobbing behavior of the projectile.
*   **`direction_random_rad="0.003"`**: Introduces a small amount of randomness to the projectile's initial direction.

### Collision and Death Effects

*   **`on_death_explode="1"`**: Triggers an explosion when the projectile dies.
*   **`on_lifetime_out_explode="1"`**: Triggers an explosion when the projectile's lifetime runs out.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision.
*   **`explosion_dont_damage_shooter="1"`**: The explosion will not harm the shooter.

### Explosion Configuration (`config_explosion`)

*   **`damage="0"`**: The explosion itself deals no damage.
*   **`explosion_radius="1"`**: The radius of the explosion effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma_green.xml"`**: The visual sprite used for the explosion.
*   **`physics_throw_enabled="1"`**: The explosion can impart physics force.
*   **`shake_vegetation="1"`**: The explosion will shake vegetation.
*   **`camera_shake="0"`**: The explosion does not cause camera shake.

## Visuals

### Sprite Component

*   **`image_file="data/projectiles_gfx/grenade_green.xml"`**: Specifies the graphical asset for the projectile.
*   **`emissive="1"`**, **`additive="1"`**: These flags likely contribute to how the sprite is rendered, potentially making it glow or blend additively.

### Sprite Particle Emitter Component

This component adds a particle effect to the projectile, likely for visual flair or to indicate its healing nature.

*   **`sprite_file="data/particles/heal.xml"`**: The sprite file used for the emitted particles.
*   **`emission_interval_min_frames="4"`**, **`emission_interval_max_frames="8"`**: Controls the timing of particle emissions.
*   **`count_min="1"`**, **`count_max="1"`**: The number of particles emitted per interval.
*   **`randomize_rotation`**, **`randomize_angular_velocity`**, **`randomize_position`**, **`randomize_velocity`**: These attributes introduce variations in the emitted particles' properties.

## Audio

### Audio Component

*   **`file="data/audio/Desktop/projectiles.bank"`**: The audio bank containing the sound effects.
*   **`event_root="projectiles/bullet_heal_robot"`**: The specific sound event triggered for this projectile.

## Variables

### Variable Storage Component

*   **`name="projectile_file"`**: Stores the path to this entity's XML file, useful for referencing it elsewhere.
*   **`value_string="data/entities/projectiles/healshot.xml"`**: The actual file path.