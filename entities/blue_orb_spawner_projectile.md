---
title: Blue Orb Spawner Projectile
category: entities
---

# Blue Orb Spawner Projectile

This entity defines the behavior and appearance of the "Blue Orb Spawner" projectile in Noita. It's a projectile that doesn't deal direct damage but instead explodes on impact or after a set lifetime, creating a visual effect and potentially a hole in the environment.

## Key Components and Attributes

### Base Projectile Properties

The projectile inherits fundamental properties from `base_projectile.xml`.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance.
    *   `mass="0.06"`: A small mass value.

### Projectile Component

This component governs the projectile's specific behaviors.

*   **`ProjectileComponent`**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Controls the lobbing behavior, suggesting a slight upward arc.
    *   `speed_min="0"`, `speed_max="0"`: The projectile starts with zero initial velocity.
    *   `die_on_low_velocity="0"`: Does not die if its velocity becomes too low.
    *   `on_death_explode="1"`: Explodes when it dies.
    *   `on_lifetime_out_explode="1"`: Explodes when its lifetime expires.
    *   `explosion_dont_damage_shooter="1"`: The explosion does not harm the entity that fired it.
    *   `bounce_always="1"`: The projectile will always bounce off surfaces.
    *   `damage="0.1"`: Deals a very small amount of damage.
    *   `on_collision_die="0"`: Does not die upon collision.
    *   `lifetime="10"`: The projectile exists for 10 frames before expiring.

#### `config_explosion` (Nested within `ProjectileComponent`)

Defines the parameters of the explosion.

*   `never_cache="1"`: Prevents caching of this explosion.
*   `camera_shake="0"`: No camera shake on explosion.
*   `explosion_radius="10"`: The radius of the explosion.
*   `explosion_sprite="data/particles/explosion_016_plasma.xml"`: The visual effect used for the explosion.
*   `ray_energy="10000"`: High energy for raycasting effects.
*   `hole_destroy_liquid="1"`: The explosion can destroy liquids.
*   `explosion_sprite_emissive="1"`, `explosion_sprite_additive="1"`: The explosion sprite is emissive and uses additive blending.
*   `hole_enabled="1"`: Creates a hole in the environment.
*   `physics_explosion_power.min="0.2"`, `physics_explosion_power.max="0.3"`: The force of the physics-based explosion.
*   `physics_throw_enabled="1"`: Objects affected by the explosion are thrown.
*   `shake_vegetation="1"`: Vegetation is shaken by the explosion.
*   `audio_event_name="explosions/magic_small"`: The sound event played on explosion.

### Sprite Components

These components define the visual representation of the projectile.

*   **`SpriteComponent` (x2)**:
    *   `image_file="data/projectiles_gfx/orb_blue.xml"`: Specifies the sprite sheet for the orb.
    *   `rect_animation="spawn"`: Uses the "spawn" animation from the sprite sheet.
    *   `offset_x="6"`, `offset_y="6"`: Offsets the sprite's position.
    *   The second `SpriteComponent` has `emissive="1"` and `additive="1"`, indicating it contributes to lighting and uses additive blending for a glowing effect.

### Lua Component

*   **`LuaComponent`**:
    *   `script_source_file="data/scripts/projectiles/orbspawn_blue.lua"`: Links to a Lua script that likely handles additional logic for this projectile.
    *   `remove_after_executed="1"`: The Lua script will be removed after it runs.

### Light Component

*   **`LightComponent`**:
    *   `radius="150"`: The radius of the light emitted by the projectile.
    *   `r="30"`, `g="90"`, `b="30"`: Defines the greenish color of the light.

### Audio Component

*   **`AudioComponent`**:
    *   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank.
    *   `event_root="projectiles/orb_a"`: The root event for projectile sounds.

### Variable Storage Component

*   **`VariableStorageComponent`**:
    *   `name="projectile_file"`: Stores the path to this entity's XML file, useful for referencing.
    *   `value_string="data/entities/projectiles/orbspawner_blue.xml"`: The value is the path to this entity.