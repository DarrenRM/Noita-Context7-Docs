---
title: Arrow Projectile
category: entities
---

# Arrow Projectile

This document details the configuration of the `arrow.xml` entity, defining its behavior and appearance as a player projectile in Noita.

## Core Entity Configuration

The `Entity` tag defines the base properties of the arrow projectile.

*   **`name`**: `$projectile_default` - Indicates this entity uses the default projectile naming convention.
*   **`tags`**: `projectile_player` - Assigns the projectile to the player's category, influencing interactions and targeting.

## Base Projectile Properties

The `<Base file="data/entities/base_projectile.xml">` tag inherits common projectile functionalities.

### Velocity Component

Defines the physical movement characteristics of the arrow.

*   **`gravity_y`**: `250` - The strength of gravitational pull affecting the projectile vertically.
*   **`air_friction`**: `0.8` - The resistance the projectile experiences from the air, slowing it down.
*   **`mass`**: `0.35` - The projectile's mass, influencing its momentum and interaction with physics.

## Projectile Component

This is the primary component defining the arrow's unique projectile behavior.

### Key Attributes:

*   **`lob_min` / `lob_max`**: `0.5` / `0.7` - Controls the minimum and maximum vertical deviation (lob) of the projectile's trajectory.
*   **`speed_min` / `speed_max`**: `550` / `650` - Sets the range for the projectile's initial launch speed.
*   **`friction`**: `1` - A multiplier for how much friction affects the projectile's speed.
*   **`direction_random_rad`**: `0.01` - Introduces a small amount of randomness to the projectile's initial direction in radians.
*   **`on_death_explode`**: `0` - The projectile does not explode upon death.
*   **`on_death_gfx_leave_sprite`**: `1` - Leaves a sprite graphic when it dies.
*   **`on_lifetime_out_explode`**: `0` - The projectile does not explode when its lifetime expires.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon colliding with an entity.
*   **`lifetime`**: `750` - The duration in frames the projectile exists before expiring.
*   **`damage`**: `0` - The base damage dealt by the projectile.
*   **`damage_scaled_by_speed`**: `1` - The projectile's damage is scaled based on its current speed.
*   **`bounces_left`**: `1` - The projectile can bounce once before being destroyed.
*   **`friendly_fire`**: `1` - The projectile can damage friendly entities.
*   **`knockback_force`**: `1.0` - The force applied to entities when hit by the projectile.
*   **`physics_impulse_coeff`**: `500` - A coefficient influencing the impulse applied during physics interactions.

### Damage by Type:

*   **`slice`**: `0.2` - Defines a damage multiplier for specific damage types (e.g., slicing damage).

### Explosion Configuration:

*   **`damage`**: `0` - The explosion damage (not applicable here as `on_death_explode` is 0).
*   **`explosion_radius`**: `1` - The radius of the explosion (not applicable here).

## Sprite Component

Defines the visual representation of the arrow.

*   **`image_file`**: `data/projectiles_gfx/arrow.xml` - Specifies the XML file containing the arrow's sprite data and animations.

## Particle Emitter Component

Adds visual effects, specifically a trail of sparks.

*   **`emitted_material_name`**: `spark_white` - The material used for the emitted particles.
*   **`is_trail`**: `1` - Indicates that these particles form a trail behind the projectile.
*   **`render_on_grid`**: `1` - The particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.

## Audio Component

Handles sound effects associated with the arrow.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound events.
*   **`event_root`**: `player_projectiles/bullet_arrow` - The specific sound event for the arrow projectile.

## Variable Storage Component

Stores custom variables for the entity.

*   **`name`**: `projectile_file` - The name of the variable.
*   **`value_string`**: `data/entities/projectiles/deck/arrow.xml` - The value, pointing to the entity's own file path.