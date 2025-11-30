---
title: Orb Boss Limbs Projectile
category: entities
---

# Orb Boss Limbs Projectile

This entity defines a projectile used by the "Orb Boss" in Noita. It's designed to be a fast-moving, explosive projectile with a distinct visual and light effect.

## Key Components and Attributes

### Base Entity

*   **`name`**: `$animal_orb_boss_limbs` - The internal identifier for this entity.
*   **`Base file="data/entities/base_projectile.xml"`**: Inherits core projectile properties.
    *   **`VelocityComponent`**:
        *   `gravity_y="0"`: The projectile is not affected by gravity.
        *   `air_friction="0"`: No air resistance.

### Projectile Component

*   **`ProjectileComponent`**: Defines the behavior and properties of the projectile.
    *   **`lob_min="0.8"`, `lob_max="1.0"`**: Controls the lobbing behavior, suggesting a relatively straight trajectory.
    *   **`speed_min="150"`, `speed_max="150"`**: The projectile travels at a constant speed of 150 units.
    *   **`die_on_low_velocity="0"`**: The projectile does not die if its velocity drops too low.
    *   **`on_death_explode="1"`**: The projectile explodes when it dies.
    *   **`on_lifetime_out_explode="1"`**: The projectile explodes when its lifetime expires.
    *   **`explosion_dont_damage_shooter="1"`**: The explosion will not harm the entity that fired it.
    *   **`damage="0.8"`**: The projectile itself deals a small amount of damage.
    *   **`on_collision_die="1"`**: The projectile dies upon colliding with something.
    *   **`lifetime="100"`**: The projectile exists for 100 frames before expiring.

#### `config_explosion` (within `ProjectileComponent`)

*   **`never_cache="1"`**: Ensures the explosion effect is always generated fresh.
*   **`camera_shake="0"`**: No camera shake is applied by this explosion.
*   **`explosion_radius="9"`**: The radius of the explosion.
*   **`explosion_sprite="data/particles/explosion_016_plasma_pink.xml"`**: Specifies the visual sprite for the explosion.
*   **`explosion_sprite_additive="1"`, `explosion_sprite_emissive="1"`**: The explosion sprite uses additive blending and is emissive.
*   **`ray_energy="5000"`**: The energy of any rays produced by the explosion.
*   **`hole_destroy_liquid="1"`, `hole_enabled="1"`**: The explosion creates holes and destroys liquids.
*   **`hole_image="data/temp/explosion_hole.png"`**: The image used for the explosion hole.
*   **`physics_explosion_power.max="0.3"`**: The maximum force applied by the explosion to physics objects.
*   **`shake_vegetation="1"`**: The explosion will shake vegetation.
*   **`light_fade_time="0.8"`, `light_r="10"`, `light_g="60"`, `light_b="10"`**: Defines a short-lived, greenish light effect for the explosion.

### Sprite Components

There are two `SpriteComponent`s, both using `data/projectiles_gfx/orb_pink.xml`. This suggests a layered or duplicated sprite for visual emphasis.

*   **`image_file="data/projectiles_gfx/orb_pink.xml"`**: The graphical asset for the projectile.
*   **`offset_x="6"`, `offset_y="6"`**: Offsets for the sprite's position.
*   **`rect_animation="spawn"`**: Uses a "spawn" animation.
*   The second `SpriteComponent` has `emissive="1"` and `additive="1"`, contributing to a glowing effect.

### Light Component

*   **`LightComponent`**: Adds a persistent light source to the projectile.
    *   **`radius="150"`**: The radius of the light.
    *   **`r="30"`, `g="30"`, `b="90"`**: A bluish light color.

### Lua Component

*   **`LuaComponent`**: Attaches a Lua script to the entity for custom behavior.
    *   **`script_source_file="data/scripts/projectiles/orb_blue.lua"`**: The script controlling additional logic.
    *   **`execute_every_n_frame="5"`**: The script runs every 5 frames.