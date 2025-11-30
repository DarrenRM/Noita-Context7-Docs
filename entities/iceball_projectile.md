---
title: Iceball Projectile
category: entities
---

# Iceball Projectile

This document details the configuration of the `iceball.xml` entity, representing the iceball projectile in Noita. This projectile is designed to deal ice damage, freeze enemies, and create a chilling explosion upon impact.

## Core Components

### Base Projectile (`Base file="data/entities/base_projectile.xml"`)

This component defines fundamental projectile properties.

*   **`gravity_y`**: `100` - Controls the downward acceleration due to gravity.
*   **`mass`**: `0.09` - The mass of the projectile, influencing its interaction with physics.

### Projectile (`ProjectileComponent`)

This is the primary component defining the iceball's behavior.

*   **`lob_min` / `lob_max`**: `0.8` / `1.0` - Affects the arc of the projectile.
*   **`speed_min` / `speed_max`**: `160` / `170` - The initial velocity range of the projectile.
*   **`die_on_low_velocity`**: `1` - The projectile will be destroyed if its velocity drops too low.
*   **`on_death_explode`**: `1` - The projectile explodes when it dies.
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`die_on_liquid_collision`**: `1` - The projectile is destroyed upon colliding with liquids.
*   **`damage`**: `0` - Base damage dealt by the projectile itself (before type-specific modifiers).
*   **`lifetime`**: `60` - The duration in frames before the projectile is destroyed if it hasn't collided.
*   **`damage_game_effect_entities`**: `data/entities/misc/effect_frozen_short.xml` - Applies a short-term freezing effect to entities hit.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_large_blue.xml` - The visual effect at the point of origin.
*   **`shoot_light_flash_r` / `g` / `b` / `radius`**: `10` / `140` / `255` / `150` - Defines the color and radius of the light flash when fired.
*   **`knockback_force`**: `1.5` - The force applied to push entities away upon impact.
*   **`physics_impulse_coeff`**: `2800` - Coefficient for physics impulse calculations.

#### Damage by Type (`damage_by_type`)

*   **`ice`**: `0.25` - The projectile deals 0.25 damage of type 'ice'.

#### Explosion Configuration (`config_explosion`)

Defines the properties of the explosion when the projectile dies.

*   **`camera_shake`**: `7.5` - The intensity of camera shake during the explosion.
*   **`explosion_radius`**: `15` - The area of effect for the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_040_poof_blue.xml` - The visual sprite for the explosion.
*   **`create_cell_probability`**: `100` - Always creates cells upon explosion.
*   **`create_cell_material`**: `blood_cold` - The material of the cells created.
*   **`hole_enabled`**: `1` - Creates holes in surfaces.
*   **`damage`**: `2` - Damage dealt by the explosion.
*   **`ray_energy`**: `50000` - Energy value for raycasting effects from the explosion.
*   **`particle_effect`**: `1` - Enables particle effects for the explosion.
*   **`damage_mortals`**: `1` - The explosion damages mortal entities.
*   **`physics_explosion_power.min` / `max`**: `0.6` / `0.9` - The range of physics force applied by the explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake.
*   **`sparks_enabled`**: `1` - Enables spark effects.
*   **`spark_material`**: `spark_blue` - The material of the sparks.

### Sprite (`SpriteComponent`)

Defines the visual appearance of the iceball.

*   **`image_file`**: `data/projectiles_gfx/fireball_alt_ice.xml` - The sprite asset used.
*   **`offset_x` / `offset_y`**: `16` / `12` - Offset for positioning the sprite.
*   **`additive`**: `1` - Enables additive blending for the sprite, making it appear brighter.

### Particle Emitters (`ParticleEmitterComponent`)

Multiple emitters contribute to the visual effects of the iceball.

*   **Emitter 1 (Smoke)**:
    *   `emitted_material_name`: `smoke`
    *   `count_min`/`max`: `5`
    *   `lifetime_min`/`max`: `0.1` / `0.3`
*   **Emitter 2 (Blue Sparks)**:
    *   `emitted_material_name`: `spark_blue`
    *   `is_trail`: `1`
    *   `render_on_grid`: `1`
    *   `fade_based_on_lifetime`: `1`
    *   `emit_cosmetic_particles`: `1`
*   **Emitter 3 (Snow)**:
    *   `emitted_material_name`: `snow`
    *   `count_min`/`max`: `1`
    *   `lifetime_min`/`max`: `0.1` / `0.3`

### Sprite Particle Emitter (`SpriteParticleEmitterComponent`)

*   **`sprite_file`**: `data/particles/smoke_icy.xml` - Uses a specific icy smoke sprite.
*   **`color_change.a`**: `-2` - Controls the alpha fade-out of the particles.
*   **`randomize_position`**: Defines the spread of emitted particles.
*   **`randomize_velocity`**: Defines the initial velocity variation of particles.

### Light Component (`LightComponent`)

*   **`radius`**: `150` - The radius of the light emitted by the projectile.

### Material Converter (`Base file="data/entities/misc/material_converter_freeze.xml"`)

This component, inherited from a separate entity, handles the freezing effect.

*   **`MagicConvertMaterialComponent` (First Instance)**:
    *   `steps_per_frame`: `20`
    *   `loop`: `1`
    *   `radius`: `20`
*   **`MagicConvertMaterialComponent` (Second Instance)**:
    *   `kill_when_finished`: `0`
    *   `extinguish_fire`: `1`
    *   `loop`: `1`
    *   `radius`: `30`

### Audio Component (`AudioComponent`)

*   **`file`**: `data/audio/Desktop/projectiles.bank`
*   **`event_root`**: `player_projectiles/bullet_fire_heavy` - The sound event triggered when firing.

### Variable Storage (`VariableStorageComponent`)

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/deck/iceball.xml` - Stores the entity's own file path.