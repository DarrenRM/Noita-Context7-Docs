---
title: X-Ray Projectile
category: entities
---

# X-Ray Projectile

This entity defines a projectile that creates an X-Ray effect. It's designed to reveal hidden elements within the game world.

## Key Components and Attributes

### ProjectileComponent

This is the core component for defining projectile behavior.

*   **`_enabled`**: `1` - Enables the projectile.
*   **`lob_min`, `lob_max`**: `0.8`, `1.0` - Controls the lobbing behavior, suggesting a mostly straight trajectory.
*   **`speed_min`, `speed_max`**: `0`, `0` - The projectile has no initial speed.
*   **`friction`**: `3.0` - High friction, causing it to slow down quickly if it had speed.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`ground_collision_fx`**: `1` - Plays a visual effect on ground collision.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion does not harm the entity that shot it.
*   **`on_collision_die`**: `1` - The projectile dies upon colliding with something.
*   **`lifetime`**: `1000` - The projectile exists for 1000 frames.
*   **`damage`**: `0.000` - Deals no direct damage.
*   **`penetrate_world`**: `1` - Allows the projectile to pass through world geometry.
*   **`shoot_light_flash_radius`**: `200` - Creates a light flash with a radius of 200 when shot.
*   **`shoot_light_flash_r`, `g`, `b`**: `255`, `150`, `255` - Defines the color of the light flash (pinkish).
*   **`damage_every_x_frames`**: `20` - Damage is applied every 20 frames (though damage is 0).

#### `config_explosion`

Defines the properties of the explosion when the projectile dies.

*   **`never_cache`**: `1` - Prevents caching of this explosion.
*   **`camera_shake`**: `0` - No camera shake from the explosion.
*   **`explosion_radius`**: `0` - No explosion radius.
*   **`damage`**: `0` - The explosion deals no damage.
*   **`ray_energy`**: `10` - This is a key attribute for the X-ray effect, indicating energy for raycasting.
*   **`physics_explosion_power.min`, `.max`**: `0`, `0` - No physics-based explosion force.
*   **`sparks_enabled`**: `0` - No sparks are generated.
*   **`gore_particle_count`**: `0` - No gore particles.

### MagicXRayComponent

This component specifically enables the X-ray functionality.

*   **`radius`**: `512` - The X-ray effect has a radius of 512 units.
*   **`steps_per_frame`**: `8` - The X-ray effect performs 8 steps per frame for its calculations.

### LuaComponent

This component links the projectile to a Lua script for custom behavior.

*   **`_enabled`**: `1` - Enables the Lua script.
*   **`remove_after_executed`**: `1` - The Lua component is removed after its script runs.
*   **`script_source_file`**: `data/scripts/projectiles/xray_effect.lua` - Specifies the Lua script responsible for the X-ray effect logic.

### AudioComponent

Handles the sound effects associated with the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/all_seeing_eye` - The specific sound event for this projectile.