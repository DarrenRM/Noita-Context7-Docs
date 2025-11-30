---
title: Slime Projectile
category: entities
---

# Slime Projectile

This document details the configuration of the Slime projectile entity in Noita, useful for AI-assisted modding.

## Core Entity Configuration

The `Entity` tag defines the fundamental properties of the projectile.

-   **`tags`**: `hittable, projectile_player` - Indicates the projectile can be hit and is a player-created projectile.
-   **`name`**: `$projectile_default` - A placeholder name, typically overridden by specific projectile types.

## Base Projectile Properties

The `Base` component inherits common projectile behaviors.

### `Base.VelocityComponent`

Controls the projectile's movement physics.

-   **`gravity_y`**: `10` - The strength of gravity applied to the projectile.
-   **`air_friction`**: `0` - No air resistance.
-   **`mass`**: `0.055` - The projectile's mass, affecting its interaction with physics.

## Projectile Behavior (`ProjectileComponent`)

This component defines the projectile's specific actions and effects.

-   **`speed_min`**: `90` - Minimum initial velocity.
-   **`speed_max`**: `115` - Maximum initial velocity.
-   **`on_death_explode`**: `1` - The projectile explodes upon death.
-   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
-   **`on_collision_die`**: `1` - The projectile dies upon collision.
-   **`damage`**: `0.25` - Base damage dealt by the projectile.
-   **`lifetime`**: `330` - Duration in frames before expiring.
-   **`knockback_force`**: `1.5` - The force applied to knock back entities on impact.
-   **`physics_impulse_coeff`**: `8000` - Coefficient for physics impulse calculations.

### `ProjectileComponent.config_explosion`

Defines the properties of the explosion when the projectile dies.

-   **`damage`**: `0.3` - Damage dealt by the explosion.
-   **`camera_shake`**: `3.5` - Intensity of camera shake during the explosion.
-   **`explosion_radius`**: `9` - The radius of the explosion effect.
-   **`explosion_sprite`**: `data/particles/explosion_032_slimeburst.xml` - The visual effect for the explosion.
-   **`create_cell_probability`**: `5` - Chance to create a liquid cell.
-   **`create_cell_material`**: `radioactive_liquid_fading` - The material of the created liquid cell.
-   **`hole_enabled`**: `1` - Creates a hole in surfaces.
-   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
-   **`physics_explosion_power.max`**: `0.3` - Maximum physics power of the explosion.
-   **`shake_vegetation`**: `1` - Causes vegetation to shake.
-   **`stains_enabled`**: `1` - Leaves stains on surfaces.
-   **`stains_radius`**: `9` - The radius of the stains.

## Visual Representation (`SpriteComponent`)

Defines the projectile's appearance.

-   **`image_file`**: `data/projectiles_gfx/slime.xml` - The sprite sheet or animation definition.
-   **`offset_x`**: `8` - Horizontal offset of the sprite.
-   **`offset_y`**: `6` - Vertical offset of the sprite.

## Particle Effects (`ParticleEmitterComponent`)

Manages the emission of particles.

-   **`emitted_material_name`**: `radioactive_liquid_fading` - The material of the emitted particles.
-   **`count_min`**: `1`, **`count_max`**: `2` - Number of particles emitted per burst.
-   **`is_trail`**: `1` - Indicates this is a trail emitter.
-   **`trail_gap`**: `2.5` - Spacing between trail particles.
-   **`lifetime_min`**: `0.1`, **`lifetime_max`**: `1.3` - Duration of emitted particles.
-   **`emit_cosmetic_particles`**: `1` - Emits cosmetic particles.

## Lighting (`LightComponent`)

Adds a light source to the projectile.

-   **`radius`**: `30` - The radius of the light.
-   **`r`, `g`, `b`**: `99`, `205`, `139` - RGB color values for the light (a greenish hue).

## Damage Model (`DamageModelComponent`)

Defines how the projectile takes damage and interacts with health.

-   **`hp`**: `0.2` - Hit points of the projectile.
-   **`blood_material`**: `radioactive_liquid_fading` - The material left when the projectile is damaged.

## Audio (`AudioComponent`)

Handles sound effects for the projectile.

-   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sounds.
-   **`event_root`**: `player_projectiles/bullet_slime` - The specific sound event for this projectile.

## Variable Storage (`VariableStorageComponent`)

Stores custom variables for the entity.

-   **`name`**: `projectile_file`
-   **`value_string`**: `data/entities/projectiles/deck/slime.xml` - Stores the path to this entity's XML file.