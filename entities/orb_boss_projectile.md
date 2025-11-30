---
title: Orb Boss Projectile
category: entities
---

---

# Orb Boss Projectile

This document describes the `orb_boss_limbs.xml` entity, which defines the behavior and appearance of a projectile fired by a boss.

## Key Components and Attributes

### Base Projectile (`<Base file="data/entities/base_projectile.xml">`)

This component inherits fundamental projectile properties.

*   **`VelocityComponent`**:
    *   `gravity_y="0"`: The projectile is not affected by gravity.
    *   `air_friction="0"`: No air resistance acts on the projectile.

### Projectile Component (`<ProjectileComponent>`)

Defines the core mechanics of the projectile.

*   **`_enabled="1"`**: The component is active.
*   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, influencing the arc of the projectile.
*   **`speed_min="150"`, `speed_max="150"`**: Sets a fixed speed for the projectile.
*   **`die_on_low_velocity="0"`**: The projectile does not disappear if its speed drops too low.
*   **`on_death_explode="1"`**: The projectile explodes upon death.
*   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter="1"`**: The explosion does not harm the entity that fired it.
*   **`damage="1.1"`**: The amount of damage the projectile inflicts.
*   **`on_collision_die="1"`**: The projectile is destroyed upon collision with another entity.
*   **`lifetime="100"`**: The duration in frames before the projectile expires.

#### Explosion Configuration (`<config_explosion>`)

Details the effects of the projectile's explosion.

*   **`never_cache="1"`**: Ensures the explosion effect is always generated fresh.
*   **`camera_shake="0"`**: No camera shake is triggered by the explosion.
*   **`explosion_radius="9"`**: The radius of the explosion's effect.
*   **`explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`**: The visual sprite used for the explosion.
*   **`ray_energy="5000"`**: The energy level of any rays emitted by the explosion.
*   **`hole_destroy_liquid="1"`**: The explosion can destroy liquids.
*   **`hole_enabled="1"`**: The explosion creates holes in surfaces.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the created holes.
*   **`damage_mortals="0"`**: The explosion does not damage mortal entities.
*   **`physics_explosion_power.max="0.3"`**: The maximum force of the physics-based explosion.
*   **`shake_vegetation="1"`**: The explosion can shake vegetation.
*   **`light_r="10"`, `light_g="60"`, `light_b="10"`**: The RGB values for the light emitted by the explosion.

### Sprite Components (`<SpriteComponent>`)

Define the visual appearance of the projectile.

*   **`image_file="data/projectiles_gfx/orb_pink.xml"`**: Specifies the sprite sheet for the projectile's graphics.
*   **`offset_x="6"`, `offset_y="6"`**: Adjusts the sprite's position relative to the entity's origin.
*   **`rect_animation="spawn"`**: Indicates the animation state to use.
*   **`emissive="1"`, `additive="1"`**: These flags suggest the sprite uses additive blending and emits light, contributing to its visual glow.

### Light Component (`<LightComponent>`)

Adds a light source to the projectile.

*   **`radius="150"`**: The radius of the light emitted.
*   **`r="30"`, `g="30"`, `b="90"`**: The RGB color of the light.

### Lua Component (`<LuaComponent>`)

Attaches custom Lua scripting to the projectile.

*   **`script_source_file="data/entities/animals/boss_limbs/orb_boss_limbs.lua"`**: The path to the Lua script that controls additional behaviors.
*   **`execute_every_n_frame="5"`**: The script will execute every 5 frames.

### Variable Storage Component (`<VariableStorageComponent>`)

Stores custom variables for the entity.

*   **`name="projectile_file"`**: The name of the variable.
*   **`value_string="data/entities/animals/boss_limbs/orb_boss_limbs.xml"`**: The value of the variable, likely referencing its own entity file.