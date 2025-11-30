---
title: Sniper Bullet Hell Projectile
category: entities
---

# Sniper Bullet Hell Projectile

This document details the configuration for a sniper bullet projectile in Noita, designed for AI-assisted modding.

## Core Components

### Entity Definition

The projectile is based on the `base_projectile.xml` entity, inheriting its fundamental properties.

```xml
<Entity name="$projectile_default">
    <Base file="data/entities/base_projectile.xml">
        <!-- Velocity and physics properties -->
    </Base>
    <!-- Other components -->
</Entity>
```

### Projectile Component

This is the primary component defining the projectile's behavior and characteristics.

#### Key Attributes:

*   **`friendly_fire`**: `1` - Allows the projectile to damage friendly entities.
*   **`lob_min`, `lob_max`**: `0.8`, `1.2` - Controls the minimum and maximum lob angle, influencing trajectory.
*   **`speed_min`, `speed_max`**: `350`, `1650` - Defines the range of projectile speed.
*   **`damage_scaled_by_speed`**: `1` - The projectile's damage increases with its speed.
*   **`direction_random_rad`**: `0.04` - Introduces a small amount of randomness to the projectile's direction.
*   **`on_death_explode`**: `1` - The projectile explodes upon death (e.g., hitting a surface or expiring).
*   **`on_lifetime_out_explode`**: `1` - The projectile explodes when its lifetime expires.
*   **`explosion_dont_damage_shooter`**: `1` - The explosion from this projectile will not harm the entity that fired it.
*   **`on_collision_die`**: `1` - The projectile is destroyed upon collision.
*   **`ragdoll_fx_on_collision`**: `BLOOD_SPRAY` - Applies a blood spray effect when the projectile collides.
*   **`lifetime`**: `50` - The duration in frames before the projectile expires.
*   **`ground_penetration_coeff`**: `2` - Controls how effectively the projectile penetrates ground surfaces.
*   **`camera_shake_when_shot`**: `2.0` - The intensity of camera shake when this projectile is fired.
*   **`shoot_light_flash_radius`**: `64` - The radius of the light flash effect when the projectile is shot.
*   **`create_shell_casing`**: `1` - Generates a shell casing effect when fired.
*   **`damage`**: `1.4` - The base damage of the projectile.
*   **`knockback_force`**: `4.0` - The force applied to entities that are hit by the projectile.
*   **`muzzle_flash_file`**: `data/entities/particles/muzzle_flashes/muzzle_flash_large.xml` - Specifies the particle effect for the muzzle flash.

#### Explosion Configuration (`config_explosion`):

This nested element defines the properties of the explosion that occurs when the projectile dies.

*   **`damage`**: `0.8` - Damage dealt by the explosion.
*   **`camera_shake`**: `0.5` - Camera shake intensity for the explosion.
*   **`explosion_radius`**: `3` - The radius of the explosion.
*   **`explosion_sprite`**: `data/particles/explosion_008.xml` - The visual sprite for the explosion.
*   **`hole_enabled`**: `1` - Enables the creation of holes in surfaces.
*   **`hole_image`**: `data/temp/explosion_hole.png` - The image used for the explosion hole.
*   **`ray_energy`**: `800000` - The energy of the explosion's rays.
*   **`max_durability_to_destroy`**: `10` - Maximum durability of objects that can be destroyed by the explosion.
*   **`physics_explosion_power.min`, `physics_explosion_power.max`**: `0.5`, `1.5` - Minimum and maximum physics force applied by the explosion.
*   **`physics_throw_enabled`**: `1` - Enables physics-based throwing of debris by the explosion.
*   **`shake_vegetation`**: `1` - Causes vegetation to shake from the explosion.
*   **`sparks_count_min`, `sparks_count_max`**: `15`, `30` - Range for the number of sparks generated.
*   **`material_sparks_enabled`**: `1` - Enables sparks from destroyed materials.
*   **`stains_enabled`**: `1` - Enables stain effects from the explosion.
*   **`stains_radius`**: `3` - The radius of the stains.

```xml
<ProjectileComponent
    _enabled="1"
    friendly_fire="1"
    lob_min="0.8"
    lob_max="1.2"
    speed_min="350"
    speed_max="1650"
    damage_scaled_by_speed="1"
    direction_random_rad="0.04"
    on_death_explode="1"
    on_lifetime_out_explode="1"
    explosion_dont_damage_shooter="1"
    on_collision_die="1"
    ragdoll_fx_on_collision="BLOOD_SPRAY"
    lifetime="50"
    ground_penetration_coeff="2"
    velocity_sets_scale="1"
    camera_shake_when_shot="2.0"
    shoot_light_flash_radius="64"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="1"
    bounces_left="0"
    damage="1.4"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_large.xml"
    knockback_force="4.0">
    <config_explosion
        never_cache="1"
        damage="0.8"
        camera_shake="0.5"
        explosion_radius="3"
        explosion_sprite="data/particles/explosion_008.xml"
        explosion_sprite_lifetime="0"
        create_cell_probability="0"
        hole_destroy_liquid="0"
        hole_enabled="1"
        hole_image="data/temp/explosion_hole.png"
        ray_energy="800000"
        max_durability_to_destroy="10"
        particle_effect="0"
        physics_explosion_power.min="0.5"
        physics_explosion_power.max="1.5"
        physics_throw_enabled="1"
        shake_vegetation="1"
        sparks_count_max="30"
        sparks_count_min="15"
        material_sparks_enabled="1"
        material_sparks_count_max="2"
        material_sparks_count_min="0"
        sparks_enabled="0"
        light_enabled="0"
        stains_enabled="1"
        stains_radius="3">
    </config_explosion>
</ProjectileComponent>
```

### Sprite Component

Defines the visual appearance of the projectile.

*   **`image_file`**: `data/projectiles_gfx/bullet.xml` - The file containing the bullet's sprite data.
*   **`emissive`**: `1` - The sprite emits light.
*   **`additive`**: `1` - The sprite uses additive blending.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/bullet.xml"
    next_rect_animation=""
    rect_animation=""
    emissive="1"
    additive="1">
</SpriteComponent>
```

### Audio Components

These components handle the sound effects associated with the projectile.

*   **`AudioComponent`**: Plays a sound event when the projectile is fired or impacts.
    *   **`file`**: `data/audio/Desktop/projectiles.bank`
    *   **`event_root`**: `projectiles/bullet_sniper_enemy`
*   **`AudioLoopComponent`**: Plays a looping sound as the projectile passes by.
    *   **`file`**: `data/audio/Desktop/projectiles.bank`
    *   **`event_name`**: `projectiles/sniper_bullet_passby`
    *   **`set_speed_parameter`**: `1` - The sound's speed parameter is set based on the projectile's velocity.
    *   **`auto_play`**: `1` - The sound starts playing automatically.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="projectiles/bullet_sniper_enemy">
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="projectiles/sniper_bullet_passby"
    set_speed_parameter="1"
    auto_play="1">
</AudioLoopComponent>
```

### Variable Storage Component

Stores variables associated with the projectile.

*   **`name`**: `projectile_file`
*   **`value_string`**: `data/entities/projectiles/sniperbullet_hell.xml` - Stores the path to this projectile's entity file.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/sniperbullet_hell.xml">
</VariableStorageComponent>
```