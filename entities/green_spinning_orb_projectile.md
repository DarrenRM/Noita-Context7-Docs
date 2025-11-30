---
title: Green Spinning Orb Projectile
category: entities
---

# Green Spinning Orb Projectile

This document details the configuration of the "Green Spinning Orb" projectile entity in Noita, focusing on its behavior, visual representation, and effects.

## Core Components

The Green Spinning Orb is a projectile entity defined by its `Base`, `ProjectileComponent`, `SpriteComponent`, `LightComponent`, `LuaComponent`, and `AudioComponent`.

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This section inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="1"`: No air friction is applied.
    *   `mass="0.05"`: Defines the projectile's mass.

### Projectile Behavior (`ProjectileComponent`)

This component governs the projectile's movement, collision, and death effects.

*   **Movement & Trajectory**:
    *   `lob_min="0.8"`, `lob_max="1.0"`: Controls the minimum and maximum lobbing behavior.
    *   `speed_min="350"`, `speed_max="350"`: Sets a fixed projectile speed.
    *   `die_on_low_velocity="0"`: The projectile does not die when its velocity becomes low.
*   **Death & Explosion**:
    *   `on_death_explode="1"`: The projectile explodes upon death.
    *   `on_lifetime_out_explode="1"`: The projectile explodes when its lifetime expires.
    *   `explosion_dont_damage_shooter="1"`: The explosion does not damage the entity that fired it.
    *   `on_collision_die="1"`: The projectile dies upon collision.
    *   `lifetime="100"`: The projectile exists for 100 frames before expiring.
*   **Collision & Interaction**:
    *   `go_through_this_material="rock_box2d_nohit"`: The projectile can pass through materials tagged as "rock\_box2d\_nohit".
*   **Damage & Knockback**:
    *   `damage="0.8"`: The projectile deals 0.8 damage.
    *   `knockback_force="1.0"`: Applies a knockback force of 1.0.
*   **Explosion Configuration (`config_explosion`)**:
    *   `never_cache="1"`: Prevents caching of this explosion effect.
    *   `camera_shake="0"`: No camera shake is applied.
    *   `explosion_radius="10"`: The explosion has a radius of 10 units.
    *   `explosion_sprite="data/particles/explosion_016_plasma_green.xml"`: Specifies the visual sprite for the explosion.
    *   `ray_energy="1000"`: The energy of the explosion's rays.
    *   `hole_destroy_liquid="1"`: The explosion can destroy liquids.
    *   `hole_enabled="1"`: Explosion holes are enabled.
    *   `hole_image="data/temp/explosion_hole.png"`: The image used for explosion holes.
    *   `explosion_sprite_emissive="1"`, `explosion_sprite_additive="1"`: The explosion sprite is emissive and additive.
    *   `physics_explosion_power.min="0.24"`, `physics_explosion_power.max="0.34"`: Defines the minimum and maximum physics force of the explosion.
    *   `shake_vegetation="1"`: The explosion shakes vegetation.
    *   `light_r="10"`, `light_g="60"`, `light_b="10"`: Defines the RGB color of the explosion's light.
    *   `light_fade_time="0.8"`: The light fades out over 0.8 seconds.

### Visual Representation (`SpriteComponent`)

Two `SpriteComponent` instances define the visual appearance of the projectile.

*   **Primary Sprite**:
    *   `image_file="data/projectiles_gfx/orb_green.xml"`: Uses the specified image file for the orb's graphics.
    *   `offset_x="6"`, `offset_y="6"`: Offsets the sprite's position.
    *   `rect_animation="spawn"`: Uses the "spawn" animation.
*   **Emissive Sprite**:
    *   `image_file="data/projectiles_gfx/orb_green.xml"`: Same image file as the primary sprite.
    *   `emissive="1"`, `additive="1"`: Makes the sprite emissive and additive, contributing to its glow.

### Lighting (`LightComponent`)

This component adds a light source to the projectile.

*   `radius="150"`: The light has a radius of 150 units.
*   `r="30"`, `g="90"`, `b="30"`: Sets the light color to a greenish hue.

### Scripting (`LuaComponent`)

This component enables custom scripting for the projectile.

*   `script_source_file="data/scripts/projectiles/orb_blue.lua"`: **Note:** This points to `orb_blue.lua`, which might be a placeholder or intended for shared logic.
*   `execute_every_n_frame="5"`: The script logic executes every 5 frames.

### Audio (`AudioComponent`)

Defines the sound effects associated with the projectile.

*   `file="data/audio/Desktop/projectiles.bank"`: Specifies the audio bank file.
*   `event_root="projectiles/orb_a"`: Sets the root event for projectile sounds.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

*   `name="projectile_file"`: The name of the variable.
*   `value_string="data/entities/projectiles/orb_green_spin.xml"`: Stores the path to this entity's XML file.