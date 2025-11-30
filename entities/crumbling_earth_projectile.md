---
title: Crumbling Earth Projectile
category: entities
---

# Crumbling Earth Projectile

This document details the configuration for the "Crumbling Earth" projectile in Noita, designed for AI-assisted modding.

## Entity Definition

The core entity defines a player projectile with specific behaviors and visual effects.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
```

### Base Projectile Configuration

Inherits fundamental projectile properties.

```xml
<Base file="data/entities/base_projectile.xml" >
    <VelocityComponent
        gravity_y="10"
        mass="0.07"
    >
    </VelocityComponent>
</Base>
```

*   **`gravity_y`**: Controls the downward acceleration of the projectile.
*   **`mass`**: Affects how the projectile interacts with physics.

### Projectile Component

Defines the unique characteristics and actions of the Crumbling Earth projectile.

```xml
<ProjectileComponent
    lifetime="30"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_magic_launcher_trailer.xml"
    shoot_light_flash_radius="120"
    shoot_light_flash_r="255"
    shoot_light_flash_g="240"
    shoot_light_flash_b="30"
    speed_min="110"
    speed_max="110"
    friction="1"
    direction_random_rad="0.00"
    on_death_explode="1"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
>
    <config_explosion
        never_cache="1"
        camera_shake="0"
        explosion_radius="2"
        explosion_sprite=""
        explosion_sprite_lifetime="0"
        create_cell_probability="0"
        hole_destroy_liquid="0"
        explosion_sprite_emissive="0"
        explosion_sprite_additive="0"
        hole_enabled="0"
        ray_energy="0"
        damage="0"
        particle_effect="0"
        damage_mortals="0"
        physics_explosion_power.min="0"
        physics_explosion_power.max="0"
        load_this_entity="data/entities/projectiles/deck/crumbling_earth_effect.xml"
        physics_throw_enabled="0"
        shake_vegetation="0"
        sparks_enabled="0"
        stains_enabled="0"
    >
    </config_explosion>
</ProjectileComponent>
```

**Key Attributes:**

*   **`lifetime`**: Duration in frames before the projectile expires.
*   **`muzzle_flash_file`**: Path to the particle effect used when the projectile is fired.
*   **`shoot_light_flash_radius`**, **`shoot_light_flash_r`**, **`shoot_light_flash_g`**, **`shoot_light_flash_b`**: Define the light emitted upon firing.
*   **`speed_min`**, **`speed_max`**: The initial velocity of the projectile.
*   **`on_death_explode`**: Triggers an explosion upon death (collision or lifetime end).
*   **`on_lifetime_out_explode`**: Triggers an explosion when the lifetime expires.
*   **`on_collision_die`**: The projectile dies upon colliding with something.
*   **`load_this_entity`**: Specifies an entity to load upon explosion, creating a secondary effect.

**`config_explosion` Summary:**

This sub-element configures the explosion behavior. For this projectile, the explosion is designed to be non-damaging and primarily visual, loading a specific effect entity.

*   **`explosion_radius`**: Size of the explosion.
*   **`damage`**: Set to `0`, indicating no damage.
*   **`load_this_entity`**: Crucially, this points to `crumbling_earth_effect.xml`, which defines the visual aftermath of the projectile's demise.
*   Most other explosion parameters are disabled or set to minimal values, focusing on the `load_this_entity` effect.

### Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/crumbling_earth">
</AudioComponent>
```

*   **`file`**: The audio bank containing the sound events.
*   **`event_root`**: The specific sound event to trigger for this projectile.