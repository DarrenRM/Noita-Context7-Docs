---
title: Wall Vertical Projectile
category: data/entities
---

# Wall Vertical Projectile

This document describes the `wall_vertical.xml` entity, which defines a player projectile in Noita. This projectile is designed to stick to walls and has specific behaviors related to its movement, collision, and visual effects.

## Key Attributes

### Base Projectile Properties

*   **`gravity_y="0"`**: The projectile is not affected by gravity, allowing it to travel in a straight line horizontally.
*   **`mass="0.04"`**: A small mass value, indicating it's lightweight.

### Projectile Component

This component governs the core behavior of the projectile.

*   **`lob_min="0.8"`, `lob_max="1.0"`**: These values suggest a very slight upward or downward trajectory bias, but with minimal variation.
*   **`speed_min="0"`, `speed_max="0"`**: The projectile has no initial speed, implying it's likely spawned with a specific velocity from a casting mechanism.
*   **`direction_random_rad="0"`**: The projectile's direction is precisely controlled, with no random deviation.
*   **`on_death_explode="0"`**: The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite="0"`**: No graphical effects are left behind when the projectile dies.
*   **`on_lifetime_out_explode="0"`**: The projectile does not explode when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: If an explosion were to occur (though disabled here), it wouldn't harm the shooter.
*   **`on_collision_die="1"`**: The projectile dies upon colliding with anything.
*   **`die_on_liquid_collision="1"`**: The projectile also dies upon colliding with liquids.
*   **`velocity_sets_scale="1"`**: The projectile's velocity influences its scale.
*   **`lifetime="3"`**: The projectile exists for 3 seconds before expiring.
*   **`damage="0"`**: This projectile deals no direct damage.
*   **`bounces_left="0"`**: The projectile cannot bounce.
*   **`penetrate_entities="1"`**: The projectile can pass through other entities.
*   **`penetrate_world="1"`**: The projectile can pass through the game world (walls, terrain).
*   **`camera_shake_when_shot="5.0"`**: Shooting this projectile causes a noticeable camera shake.
*   **`knockback_force="0.0"`**: The projectile does not apply knockback.
*   **`physics_impulse_coeff="0"`**: No physics impulse is applied upon collision.

### Light Component

*   **`radius="150"`**: The projectile emits light with a radius of 150 units.
*   **`r="30"`, `g="90"`, `b="30"`**: The light emitted is a greenish hue.

### Lua Component

*   **`script_source_file="data/scripts/projectiles/wall_vertical.lua"`**: This indicates that custom Lua scripting is used to define the projectile's specific behavior, likely for sticking to walls.
*   **`execute_every_n_frame="1"`**: The script runs every frame.
*   **`remove_after_executed="1"`**: The Lua script is removed after its first execution.

### Variable Storage Component

*   **`name="projectile_file"`**: Stores the path to this projectile's entity file.
*   **`value_string="data/entities/projectiles/deck/wall_vertical.xml"`**: The actual path to the file.

## Audio Component

*   **`file="data/audio/Desktop/projectiles.bank"`**: Specifies the audio bank used for projectile sounds.
*   **`event_root="player_projectiles/wall"`**: Indicates that sounds related to player projectiles, specifically those associated with "wall" effects, will be used.

## Summary

The `wall_vertical.xml` entity defines a player projectile that is designed to stick to surfaces. It has no initial velocity, does not deal damage, and is unaffected by gravity. Its primary function is likely to be its interaction with walls, managed by an associated Lua script. The projectile emits a greenish light and causes camera shake when fired. It can penetrate both entities and world geometry.