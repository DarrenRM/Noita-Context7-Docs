---
title: Boss Centipede Oil Orb Projectile
category: entities
---

# Boss Centipede Oil Orb Projectile

This entity defines a projectile fired by the Boss Centipede, which explodes into oil upon death or when its lifetime expires.

## Key Components

### ProjectileComponent

This component governs the projectile's behavior, including its trajectory, death conditions, and explosion properties.

*   **`lob_min`, `lob_max`**: Controls the arc of the projectile. Values are 0.8 and 1.0 respectively, indicating a relatively straight trajectory.
*   **`speed_min`, `speed_max`**: Sets the projectile's speed range between 40 and 60.
*   **`die_on_low_velocity`**: Set to `0`, meaning it won't die solely due to low speed.
*   **`on_death_explode`**: Set to `1`, causing an explosion when the projectile is destroyed.
*   **`on_lifetime_out_explode`**: Set to `1`, causing an explosion when the projectile's lifetime ends.
*   **`damage`**: Set to `0`, indicating this projectile itself does not deal direct damage.
*   **`lifetime`**: Set to `400` frames.
*   **`knockback_force`**: Set to `1.0`.

#### `config_explosion`

Defines the parameters of the explosion that occurs upon the projectile's death or lifetime expiry.

*   **`never_cache`**: Set to `1`, preventing caching of this explosion.
*   **`camera_shake`**: Set to `0`, no camera shake is applied.
*   **`explosion_radius`**: Set to `16`.
*   **`explosion_sprite`**: Specifies the visual effect of the explosion: `data/particles/explosion_016_plasma_pink.xml`.
*   **`create_cell_probability`**: Set to `100`, meaning it will always create cells.
*   **`create_cell_material`**: The material created by the explosion is `oil`.
*   **`ray_energy`**: Set to `5000`.
*   **`hole_destroy_liquid`**: Set to `1`, meaning the explosion can destroy liquids.
*   **`hole_enabled`**: Set to `1`, enabling the creation of holes.
*   **`hole_image`**: The image used for the explosion hole: `data/temp/explosion_hole.png`.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: Controls the physics force of the explosion, ranging from 0.13 to 0.23.
*   **`shake_vegetation`**: Set to `1`, causing vegetation to shake.
*   **`light_r`, `light_g`, `light_b`**: Defines the light color of the explosion (RGB: 15, 15, 40).

### ParticleEmitterComponent

This component is responsible for emitting oil particles.

*   **`emitted_material_name`**: The material emitted is `oil`.
*   **`lifetime_min`, `lifetime_max`**: The lifetime of emitted particles ranges from 3.5 to 7.5 seconds.
*   **`count_min`, `count_max`**: Emits between 2 and 4 particles per emission.
*   **`area_circle_radius.max`**: The maximum radius of the emission area is 10.
*   **`cosmetic_force_create`**: Set to `0`, these are not purely cosmetic.
*   **`emission_interval_min_frames`, `emission_interval_max_frames`**: Emits particles every 1 frame.

### SpriteComponent

Defines the visual representation of the projectile.

*   **`image_file`**: The sprite image used is `data/entities/animals/boss_centipede/orb_mat_oil_gfx.xml`.
*   **`rect_animation`**: Set to `spawn`, indicating a specific animation state.
*   **`z_index`**: Set to `0.5`, controlling its rendering layer.

### LightComponent

Adds a light source to the projectile.

*   **`radius`**: The light radius is `150`.
*   **`r`, `g`, `b`**: The light color is a dim yellow/orange (RGB: 130, 130, 90).

### AudioComponent

Handles the sound effects for the projectile.

*   **`file`**: The audio bank used is `data/audio/Desktop/projectiles.bank`.
*   **`event_root`**: The sound event category is `projectiles/magic`.

### LuaComponent

Attaches a Lua script to the entity for custom behavior.

*   **`script_source_file`**: The script is located at `data/entities/animals/boss_centipede/orb_mat_animate.lua`.
*   **`remove_after_executed`**: Set to `1`, the script is removed after its first execution.
*   **`execute_every_n_frame`**: Set to `300`, meaning the script runs every 300 frames.

### HitboxComponent

Defines the collision area of the projectile.

*   **`aabb_min_x`, `aabb_max_x`**: The bounding box extends from -9 to 9 on the X-axis.
*   **`aabb_min_y`, `aabb_max_y`**: The bounding box extends from -9 to 9 on the Y-axis.

### DamageModelComponent

Manages the entity's health and damage-related properties.

*   **`hp`**: Set to `0.6`, indicating very low health.
*   **`blood_material`**: Set to `oil`, meaning it will leave oil when damaged.
*   **`blood_multiplier`**: Set to `0`, no additional blood is generated.

### VariableStorageComponent

Stores custom variables for the entity.

*   **`name`**: `projectile_file`.
*   **`value_string`**: `data/entities/animals/boss_centipede/orb_mat_oil.xml`, likely used to reference itself.