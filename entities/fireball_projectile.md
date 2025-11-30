---
title: Fireball Projectile
category: entities
---

---

# Fireball Projectile

This document details the configuration of the "fireball" projectile entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Core Entity Properties

The `Entity` tag defines the fundamental properties of the projectile.

*   **`name`**: `$projectile_default` - A placeholder name, indicating it inherits default projectile behaviors.
*   **`tags`**: `projectile_player,fireball` - Identifies this as a player-owned projectile and specifically a fireball.

## Base Projectile Configuration

The `Base` component inherits common projectile properties.

### `Base.VelocityComponent`

Controls the physical movement and properties of the projectile.

*   **`gravity_y`**: `100` - The acceleration due to gravity affecting the projectile's vertical movement.
*   **`mass`**: `0.09` - The mass of the projectile, influencing its interaction with physics.

## Projectile Component (`ProjectileComponent`)

This is the primary component defining the projectile's behavior and effects.

### Key Attributes:

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Defines the minimum and maximum "lob" or arc of the projectile.
*   **`speed_min` / `speed_max`**: `160` / `170` - The range of initial speeds for the projectile.
*   **`die_on_low_velocity`**: `1` - The projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode`**: `1` - The projectile explodes upon death.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`die_on_liquid_collision`**: `1` - The projectile is destroyed upon contact with liquids.
*   **`damage`**: `0` - Base damage dealt by the projectile itself (before type-specific modifiers).
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision with any entity.
*   **`lifetime`**: `60` - The duration in frames before the projectile expires.
*   **`knockback_force`**: `1.5` - The force applied to entities when the projectile hits them.
*   **`physics_impulse_coeff`**: `2800` - A coefficient affecting the impulse applied during physics interactions.

### `damage_by_type`

Specifies damage multipliers for different damage types.

| Type | Multiplier |
| :--- | :--------- |
| `fire` | `0.25`     |

### `config_explosion`

Defines the properties of the explosion that occurs upon the projectile's death.

*   **`camera_shake`**: `7.5` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `15` - The radius of the explosion's effect.
*   **`explosion_sprite`**: `data/particles/explosion_040_poof.xml` - The visual effect used for the explosion.
*   **`create_cell_probability`**: `100` - The chance (in percent) of creating material cells.
*   **`create_cell_material`**: `fire` - The material of the cells created by the explosion.
*   **`hole_enabled`**: `1` - Enables the creation of holes in terrain.
*   **`damage`**: `2` - Damage dealt by the explosion itself.
*   **`ray_energy`**: `50000` - Energy value associated with the explosion's rays.
*   **`physics_explosion_power.min` / `max`**: `0.6` / `0.9` - The range of power for the physics-based explosion force.
*   **`sparks_enabled`**: `1` - Enables the emission of sparks.
*   **`sparks_count_min` / `max`**: `50` / `100` - The number of sparks emitted.
*   **`stains_enabled`**: `1` - Enables the creation of stains on surfaces.

## Visuals (`SpriteComponent`)

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/fireball_alt.xml` - The sprite sheet or animation file for the fireball.
*   **`offset_x` / `offset_y`**: `16` / `12` - Adjusts the sprite's position relative to the projectile's origin.
*   **`additive`**: `1` - Enables additive blending for the sprite, making it glow.

## Particle Emitters (`ParticleEmitterComponent`)

These components generate various particle effects associated with the projectile.

### Smoke Emitter:

*   **`emitted_material_name`**: `smoke`
*   **`count_min` / `max`**: `5` / `5`
*   **`lifetime_min` / `max`**: `0.1` / `0.3`
*   **`create_real_particles`**: `1`

### Spark Emitter:

*   **`emitted_material_name`**: `spark`
*   **`gravity.y`**: `-100.60`
*   **`is_trail`**: `1`
*   **`render_on_grid`**: `1`
*   **`fade_based_on_lifetime`**: `1`
*   **`emit_cosmetic_particles`**: `1`

### Fire Emitter:

*   **`emitted_material_name`**: `fire`
*   **`count_min` / `max`**: `1` / `1`
*   **`lifetime_min` / `max`**: `0.1` / `0.3`
*   **`create_real_particles`**: `1`

### Sprite Particle Emitter (Orange Smoke):

*   **`sprite_file`**: `data/particles/smoke_orange.xml`
*   **`additive`**: `1`
*   **`color_change.a`**: `-2` (Alpha decreases over time)
*   **`gravity.y`**: `10`
*   **`randomize_position.min_x` / `max_x`**: `2` / `12`
*   **`is_emitting`**: `1`

## Lighting (`LightComponent`)

*   **`radius`**: `150` - The radius of the light emitted by the projectile.

## Material Conversion (`MagicConvertMaterialComponent`)

This component allows the projectile to convert materials it touches.

*   **`ignite_materials`**: `99` - A value indicating the intensity or type of ignition.
*   **`radius`**: `15` - The radius of the material conversion effect.

## Audio (`AudioComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing projectile sounds.
*   **`event_root`**: `player_projectiles/bullet_fire_heavy` - The specific sound event triggered.

## Variable Storage (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/fireball.xml` - Stores the path to this entity's definition.