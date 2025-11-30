---
title: Heal Bullet (Weak) Projectile
category: entities
---

# Heal Bullet (Weak) Projectile

This document details the `heal_bullet_weak.xml` entity, which defines a weak healing projectile for Noita.

## Core Functionality

This projectile is designed to heal targets rather than damage them. It has a moderate speed and a short lifetime, exploding on collision or when its lifetime expires.

## Key Attributes

### Entity Name and Tags

*   **`name`**: `$projectile_default` (Inherited from base projectile)
*   **`tags`**: `projectile_player`, `projectile_heal` (Identifies it as a player projectile and a healing type)

### Base Projectile Settings

*   **`Base file`**: `data/entities/base_projectile.xml` (Inherits fundamental projectile properties)

### Velocity Component

*   **`gravity_y`**: `200` (Applies moderate downward gravity)
*   **`air_friction`**: `-0.5` (Slight air resistance)
*   **`mass`**: `0.05` (Lightweight projectile)

### Projectile Component

This is the primary component defining the projectile's behavior.

*   **`_enabled`**: `1` (Component is active)
*   **`lob_min`**: `0.5`, **`lob_max`**: `0.7` (Controls the arc of the projectile)
*   **`speed_min`**: `600`, **`speed_max`**: `650` (Sets the projectile's initial velocity)
*   **`friction`**: `1` (Standard friction)
*   **`direction_random_rad`**: `0.01` (Minimal deviation in projectile direction)
*   **`on_death_explode`**: `1` (Explodes when it dies)
*   **`on_lifetime_out_explode`**: `1` (Explodes when its lifetime ends)
*   **`explosion_dont_damage_shooter`**: `1` (The explosion will not harm the player who fired it)
*   **`on_collision_die`**: `1` (Dies upon colliding with something)
*   **`lifetime`**: `60` (Projectile exists for 60 frames)
*   **`lifetime_randomness`**: `7` (Adds slight variation to the lifetime)
*   **`damage`**: `0` (Does not deal damage)
*   **`friendly_fire`**: `1` (Can affect allies, though it heals)
*   **`collide_with_shooter_frames`**: `4` (Can collide with the shooter for a few frames)
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_laser_green.xml` (Visual effect upon firing)
*   **`shoot_light_flash_radius`**: `84`, **`shoot_light_flash_r`**: `110`, **`shoot_light_flash_g`**: `205`, **`shoot_light_flash_b`**: `40` (Light effect when fired)

#### Damage By Type

*   **`healing`**: `-0.15` (This is the key attribute for healing. The negative value signifies healing.)

#### Config Explosion

Defines the properties of the explosion when the projectile dies.

*   **`damage`**: `0` (The explosion itself does not deal damage)
*   **`camera_shake`**: `0.5` (Slight camera shake on explosion)
*   **`explosion_radius`**: `2` (Small explosion radius)
*   **`explosion_sprite`**: `data/particles/explosion_016_slime.xml` (Visual effect of the explosion)
*   **`hole_enabled`**: `1` (Can create small holes)
*   **`ray_energy`**: `40000` (Energy for potential ray interactions)
*   **`light_enabled`**: `1` (Creates a light source on explosion)
*   **`light_radius_coeff`**: `32`, **`light_r`**: `180`, **`light_g`**: `240`, **`light_b`**: `80` (Greenish light properties)
*   **`stains_enabled`**: `1` (Leaves stains on surfaces)
*   **`stains_radius`**: `3` (Radius of the stains)

### Particle Emitter Component

*   **`emitted_material_name`**: `spark_green` (Emits green sparks)
*   **`count_min`**: `1`, **`count_max`**: `5` (Number of sparks emitted)
*   **`lifetime_min`**: `0.1`, **`lifetime_max`**: `0.6` (Duration of sparks)
*   **`emit_cosmetic_particles`**: `1` (Emits visual-only particles)

### Audio Component

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/bullet_heal` (Sound event for healing projectiles)

### Light Component

*   **`radius`**: `40`
*   **`r`**: `180`, **`g`**: `240`, **`b`**: `50` (Greenish light)

### Variable Storage Component

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/heal_bullet_weak.xml` (Self-referential, useful for modding)