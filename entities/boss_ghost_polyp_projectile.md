---
title: Boss Ghost Polyp Projectile
category: entities
---

# Boss Ghost Polyp Projectile

This document details the `boss_ghost_polyp.xml` entity, representing a projectile fired by the Boss Ghost. It's designed to be a homing projectile with unique visual and behavioral components.

## Core Components

### Base Projectile (`BaseComponent`)

Inherits fundamental projectile properties.

*   **`gravity_y`**: `10` - Applies a downward gravitational pull.
*   **`mass`**: `0.07` - A relatively low mass, influencing its interaction with physics.

### Homing Behavior (`HomingComponent`)

Enables the projectile to track its target.

*   **`_tags`**: `polyp_homing` - Internal tag for identifying homing behavior.
*   **`homing_targeting_coeff`**: `20.0` - Strength of the homing adjustment.
*   **`homing_velocity_multiplier`**: `0.8` - Reduces velocity slightly when homing.
*   **`detect_distance`**: `200` - Range within which the projectile can detect targets.

### Projectile Mechanics (`ProjectileComponent`)

Defines the projectile's lifespan, collision, and damage properties.

*   **`speed_min`**: `200` - Minimum launch speed.
*   **`speed_max`**: `308` - Maximum launch speed.
*   **`direction_random_rad`**: `3.141592` (π) - Allows for a wide range of initial firing directions.
*   **`on_death_explode`**: `1` - Explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - Explodes when its lifetime expires.
*   **`on_collision_die`**: `1` - Dies upon colliding with something.
*   **`explosion_dont_damage_shooter`**: `1` - Prevents the explosion from harming the entity that fired it.
*   **`damage`**: `0` - Base damage of the projectile itself is zero. Damage is applied via explosion.
*   **`lifetime`**: `330` - Duration in frames before expiring.
*   **`shoot_light_flash_r/g/b`**: `90/150/10` - Defines the RGB color of a light flash when shot.
*   **`shoot_light_flash_radius`**: `48` - Radius of the light flash.
*   **`knockback_force`**: `1.0` - Amount of knockback applied on collision/explosion.
*   **`collide_with_world`**: `0` - Does not collide with the static world geometry.
*   **`penetrate_world`**: `1` - Can pass through world geometry.

#### Damage by Type

*   **`holy`**: `3.0` - Deals 3.0 damage of the 'holy' type.

#### Explosion Configuration (`config_explosion`)

Details the effects of the projectile's explosion.

*   **`never_cache`**: `1` - Ensures the explosion entity is always loaded fresh.
*   **`damage`**: `3` - Damage dealt by the explosion.
*   **`camera_shake`**: `3.5` - Intensity of camera shake upon explosion.
*   **`explosion_radius`**: `32` - The radius of the explosion's effect.
*   **`load_this_entity`**: `data/entities/particles/particle_explosion/main_blue.xml` - Specifies the visual effect for the explosion.
*   **`create_cell_material`**: `acid` - Attempts to create acid cells upon explosion.
*   **`create_cell_probability`**: `0` - The probability of creating acid cells is set to zero.
*   **`hole_enabled`**: `1` - Creates a hole in surfaces upon explosion.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`damage_mortals`**: `1` - The explosion damages living entities.
*   **`physics_explosion_power.min/max`**: `0.3/0.4` - Minimum and maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Objects affected by the explosion can be thrown.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake.
*   **`stains_enabled`**: `1` - Leaves stains on surfaces.
*   **`stains_radius`**: `9` - Radius of the stains.
*   **`audio_enabled`**: `0` - Explosion sound is disabled.

### Visuals (`SpriteComponent`)

Defines the appearance of the projectile.

*   **First Sprite (`magic_eye` tag):**
    *   **`image_file`**: `data/entities/animals/boss_ghost/polyp.xml` - Main sprite for the polyp body.
    *   **`additive`**: `1` - Uses additive blending for a glowing effect.
    *   **`emissive`**: `1` - The sprite emits light.
    *   **`z_index`**: `1.0` - Renders above other sprites.
*   **Second Sprite (`polyp_eye.xml`):**
    *   **`image_file`**: `data/entities/animals/boss_ghost/polyp_eye.xml` - Sprite for the eye.
    *   **`emissive`**: `1` - The eye sprite emits light.
    *   **`z_index`**: `0.9` - Renders slightly behind the main body.

### Hitbox (`HitboxComponent`)

Defines the collision area for the projectile.

*   **`_tags`**: `magic_eye` - Associated with the eye's hit detection.
*   **`aabb_min_x/y`**: `-5` - Minimum bounding box coordinates.
*   **`aabb_max_x/y`**: `5` - Maximum bounding box coordinates.

### Damage Model (`DamageModelComponent`)

Manages the health and damage-related properties of the projectile.

*   **`_tags`**: `magic_eye` - Associated with the eye's damage properties.
*   **`hp`**: `1.5` - Health points of the projectile.
*   **`blood_material`**: `acid` - Specifies the material left when damaged (though `blood_multiplier` is 0).
*   **`blood_multiplier`**: `0` - No blood is generated.
*   **`create_ragdoll`**: `0` - Does not create a ragdoll upon death.

### Audio (`AudioComponent`)

Handles sound effects for the projectile.

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **`event_root`**: `projectiles/acid` - The specific sound event to play.

### Variable Storage (`VariableStorageComponent`)

Stores custom variables for use by other components.

*   **`projectile_file`**: `data/entities/animals/boss_ghost/polyp_shot.xml` - Stores the file path to the projectile that this entity represents.

### Lua Scripts (`LuaComponent`)

Custom logic implemented via Lua scripts.

*   **`ethereal_check.lua`**:
    *   `execute_every_n_frame="5"`: Runs periodically to check for ethereal properties.
    *   `execute_on_added="1"`, `remove_after_executed="1"`: Runs once on entity creation to perform an initial check.
*   **`polyp_trajectory.lua`**:
    *   `execute_every_n_frame="1"`: Runs every frame to control the projectile's movement and trajectory.
*   **`polyp_remove_homing.lua`**:
    *   `execute_every_n_frame="150"`, `remove_after_executed="1"`: Runs once after 150 frames to disable homing behavior.