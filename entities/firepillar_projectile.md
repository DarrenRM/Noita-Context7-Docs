---
title: Firepillar Projectile
category: entities
---

# Firepillar Projectile

This document describes the `firepillar.xml` entity, which defines a projectile used by the boss centipede in Noita. This projectile is a fiery projectile that explodes on impact or after a set lifetime, creating a damaging area.

## Key Components

### Base Projectile Properties

The `Base` component inherits properties from `base_projectile.xml`.

*   **`VelocityComponent`**:
    *   `gravity_y`: `250` - Controls the downward acceleration due to gravity.
    *   `air_friction`: `0.05` - Resistance to movement in the air.
    *   `mass`: `0.05` - The projectile's mass, affecting its interaction with physics.

### Projectile Behavior

The `ProjectileComponent` defines the core mechanics of the firepillar.

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `40` / `60` - The range of initial projectile speeds.
*   **`die_on_low_velocity`**: `0` - The projectile does not die simply due to low speed.
*   **`on_death_explode`**: `1` - The projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion will not harm the entity that fired it.
*   **`damage`**: `0` - The projectile itself does no direct damage. Damage is applied via the explosion.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with something.
*   **`lifetime`**: `200` - The duration in frames before the projectile explodes if it hasn't already.
*   **`knockback_force`**: `1.0` - The force applied to entities hit by the projectile's explosion.

#### Damage Types

*   **`damage_by_type fire="0.8"`**: The explosion deals 0.8 damage of the 'fire' type.

#### Explosion Configuration

*   **`config_explosion`**:
    *   `never_cache`: `1` - Ensures the explosion effect is always generated fresh.
    *   `camera_shake`: `0` - No camera shake is applied.
    *   `explosion_radius`: `6` - The area of effect for the explosion.
    *   `explosion_sprite`: `data/particles/explosion_016_plasma_pink.xml` - The visual effect for the explosion.
    *   `ray_energy`: `5000` - The energy of the damaging rays emitted by the explosion.
    *   `hole_destroy_liquid`: `1` - The explosion can destroy liquids.
    *   `hole_enabled`: `1` - The explosion leaves a hole in surfaces.
    *   `hole_image`: `data/temp/explosion_hole.png` - The image used for the explosion hole.
    *   `physics_explosion_power.min` / `.max`: `0.13` / `0.23` - The minimum and maximum force of the physics-based explosion.
    *   `shake_vegetation`: `1` - The explosion will shake vegetation.
    *   `light_r` / `g` / `b`: `15` / `15` / `40` - The color of the light emitted by the explosion.

### Visuals

*   **`SpriteComponent`**:
    *   `image_file`: `data/projectiles_gfx/grenade_large.xml` - Specifies the sprite used for the projectile.
    *   `rect_animation`: `spawn` - The animation to play when the projectile spawns.

### Lighting

*   **`LightComponent`**:
    *   `radius`: `150` - The radius of the light emitted by the projectile.
    *   `r` / `g` / `b`: `130` / `35` / `90` - The color of the light.

### Scripting

*   **`LuaComponent`**:
    *   `script_source_file`: `data/entities/animals/boss_centipede/firepillar.lua` - Links to the Lua script that controls additional behavior.

### Variable Storage

*   **`VariableStorageComponent`**:
    *   `name`: `projectile_file`
    *   `value_string`: `data/entities/animals/boss_centipede/firepillar.xml` - Stores the path to this entity's XML file.