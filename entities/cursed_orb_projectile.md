---
title: Cursed Orb Projectile
category: entities
---

# Cursed Orb Projectile

This document details the configuration of the "Cursed Orb" projectile entity in Noita, primarily focusing on its behavior, visual effects, and audio.

## Base Entity

The Cursed Orb inherits its fundamental properties from `data/entities/base_projectile.xml`.

### Velocity Component

*   **`air_friction`**: `-6` - High air friction, suggesting it slows down quickly in the air.
*   **`gravity_y`**: `0` - No vertical gravity applied, meaning it travels in a straight line unless affected by other forces.
*   **`mass`**: `0.04` - A very light projectile.
*   **`terminal_velocity`**: `400` - The maximum speed it can reach due to air resistance.

## Projectile Component

This component defines the core projectile mechanics.

### Key Attributes

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Controls the arc of the projectile.
*   **`speed_min` / `speed_max`**: `1` / `2` - Defines the projectile's initial speed.
*   **`direction_random_rad`**: `0.15` - Introduces a slight random deviation in its trajectory.
*   **`die_on_liquid_collision`**: `0` - The projectile does not disappear upon hitting liquids.
*   **`on_death_explode`**: `1` - The projectile explodes when its lifetime ends or it collides.
*   **`on_lifetime_out_explode`**: `1` - Explicitly states it explodes when its lifetime expires.
*   **`friendly_fire`**: `1` - Can damage the player and allies.
*   **`shoot_light_flash_radius`**: `100` - The radius of the light flash when fired.
*   **`shoot_light_flash_r/g/b`**: `255`/`30`/`30` - Sets the color of the light flash to a reddish hue.
*   **`damage`**: `0.6` - The base damage dealt by the projectile.
*   **`lifetime`**: `120` - The duration in frames before the projectile explodes.
*   **`penetrate_entities`**: `0` - The projectile stops after hitting the first entity.
*   **`knockback_force`**: `1.5` - The force applied to entities it hits.
*   **`bounces_left`**: `2` - The projectile can bounce up to 2 times.
*   **`bounce_energy`**: `0.25` - The amount of energy retained after a bounce.
*   **`bounce_always`**: `1` - The projectile will always attempt to bounce.
*   **`bounce_at_any_angle`**: `1` - Bounces regardless of the angle of impact.
*   **`damage_game_effect_entities`**: `data/entities/misc/effect_curse_cloud_01_temporary.xml,` - Upon death, spawns a temporary curse cloud effect.

### Explosion Configuration (`config_explosion`)

*   **`never_cache`**: `1` - Ensures the explosion is always generated fresh.
*   **`camera_shake`**: `0` - No camera shake on explosion.
*   **`damage`**: `0` - The explosion itself does no direct damage.
*   **`explosion_radius`**: `1` - A very small explosion radius.
*   **`explosion_sprite`**: `data/particles/explosion_016_plasma_red.xml` - Uses a red plasma explosion sprite.
*   **`light_enabled`**: `1` - A light source is created upon explosion.
*   **`light_r/g/b`**: `255`/`30`/`30` - The light color is red.
*   **`light_radius_coeff`**: `64` - The intensity multiplier for the light radius.
*   **`shake_vegetation`**: `1` - Will shake vegetation in the vicinity of the explosion.

## Sprite Components

*   **Primary Sprite**: `data/projectiles_gfx/orb_red.xml` - Defines the visual appearance of the orb itself.
*   **Explosion Sprite**: `data/particles/explosion_016_plasma_red.xml` - Used for the visual effect of the explosion.

## Particle Emitters

Two `ParticleEmitterComponent`s are used to generate visual effects:

1.  **Trail Effect**:
    *   **`emitted_material_name`**: `spark_red_bright` - Emits bright red sparks.
    *   **`is_trail`**: `1` - Creates a continuous trail.
    *   **`lifetime_min/max`**: `1.3` / `8.9` - The duration of the emitted sparks.
    *   **`emit_cosmetic_particles`**: `1` - These are purely visual particles.

2.  **Secondary Emission**:
    *   **`emitted_material_name`**: `spark_red_bright` - Also emits bright red sparks.
    *   **`is_trail`**: `1` - Creates a trail effect.
    *   **`lifetime_min/max`**: `0.2` / `0.8` - Shorter-lived sparks.
    *   **`emit_cosmetic_particles`**: `1` - Cosmetic particles.

## Audio Components

*   **`AudioComponent`**:
    *   **`file`**: `data/audio/Desktop/projectiles.bank`
    *   **`event_root`**: `projectiles/orb_cursed` - Plays the primary sound effect for the cursed orb.
*   **`AudioLoopComponent` (x2)**:
    *   One plays a "ghost movement loop" from `animals.bank`.
    *   Another plays a "magic curse loop" from `projectiles.bank`. Both are set to auto-play.

## Variable Storage Component

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/orb_cursed.xml` - Stores the path to this entity's XML file.