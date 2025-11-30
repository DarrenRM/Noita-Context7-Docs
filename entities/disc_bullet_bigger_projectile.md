---
title: Disc Bullet Bigger Projectile
category: entities
---

# Disc Bullet Bigger Projectile

This document details the configuration for the "Disc Bullet Bigger" projectile in Noita, focusing on its attributes relevant to AI-assisted modding.

## Core Projectile Properties

The `ProjectileComponent` defines the fundamental behavior of the projectile.

### Key Attributes:

*   **`lob_min` / `lob_max`**: Controls the minimum and maximum lob angle (in radians) for the projectile's trajectory.
*   **`speed_min` / `speed_max`**: Sets the projectile's initial speed. In this case, it's a fixed `150`.
*   **`friction`**: How much the projectile's speed is reduced by air resistance.
*   **`direction_random_rad`**: Introduces a small random deviation to the projectile's initial direction.
*   **`lifetime`**: The duration (in frames) the projectile exists before expiring.
*   **`damage`**: The base damage dealt by the projectile. This is set to `0` here, indicating damage is handled by other components.
*   **`bounces_left`**: The number of times the projectile can bounce off surfaces.
*   **`bounce_at_any_angle`**: If `1`, the projectile will bounce regardless of the collision angle.
*   **`collide_with_shooter_frames`**: The number of frames after firing that the projectile will ignore collisions with the shooter.
*   **`friendly_fire`**: If `1`, the projectile can damage the player who fired it.
*   **`knockback_force`**: The force applied to entities upon collision.
*   **`physics_impulse_coeff`**: A multiplier for physics impulses, affecting how strongly the projectile interacts with physics objects.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.5"
    lob_max="0.7"
    speed_min="150"
    speed_max="150"
    friction="1"
    direction_random_rad="0.01"
    on_death_explode="0"
    on_death_gfx_leave_sprite="1"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    on_collision_die="0"
    on_collision_remove_projectile="0"
    lifetime="500"
    damage="0"
    lifetime_randomness="7"
    ragdoll_force_multiplier="0"
    hit_particle_force_multiplier="0.1"
    create_shell_casing="0"
    muzzle_flash_file="data/entities/particles/muzzle_flashes/muzzle_flash_medium.xml"
    shoot_light_flash_r="255"
    shoot_light_flash_g="240"
    shoot_light_flash_b="30"
    shoot_light_flash_radius="64"
    die_on_low_velocity="0"
    bounces_left="10"
    bounce_at_any_angle="1"
    collide_with_shooter_frames="6"
    friendly_fire="1"
    velocity_sets_rotation="1"
    velocity_sets_scale="0"
    ragdoll_fx_on_collision="BLOOD_EXPLOSION"
    knockback_force="1.3"
    physics_impulse_coeff="10000"
    >
    <damage_by_type
        slice="1.5"
        >
    </damage_by_type>
    <config_explosion>
    </config_explosion>
</ProjectileComponent>
```

## Visual and Audio Components

### Sprite Component

Defines the visual appearance of the projectile.

*   **`image_file`**: Path to the sprite definition.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/disc_bullet_bigger.xml"
    next_rect_animation=""
    rect_animation=""
     >
</SpriteComponent>
```

### Sprite Particle Emitter Component

Adds a visual trail effect to the projectile.

*   **`sprite_file`**: Path to the particle sprite definition.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: Controls the frequency of particle emission.
*   **`count_min` / `count_max`**: The number of particles emitted per interval.

```xml
<SpriteParticleEmitterComponent
    sprite_file="data/particles/discbullet_trail.xml"
    delay="0"
    lifetime="1"
    additive="1"
    color.r="1" color.g="1" color.b="1" color.a="1"
    color_change.r="0" color_change.g="0" color_change.b="0" color_change.a="-4"
    velocity.x="0" velocity.y="0"
    gravity.x="0" gravity.y="10"
    velocity_slowdown="0"
    rotation="0"
    angular_velocity="0"
    use_velocity_as_rotation="0"
    scale.x="1" scale.y="1"
    scale_velocity.x="0" scale_velocity.y="0"
    emission_interval_min_frames="5"
    emission_interval_max_frames="5"
    count_min="1" count_max="1"
    is_emitting="1"
    render_back="1"
    >
</SpriteParticleEmitterComponent>
```

### Audio Components

These components handle the sound effects associated with the projectile.

*   **`AudioComponent`**: For initial sound events (e.g., firing).
*   **`AudioLoopComponent`**: For continuous sound effects (e.g., a humming sound).

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_disc_bigger">
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/bullet_disc_bigger/loop"
    auto_play="1">
</AudioLoopComponent>
```

## Scripted Behaviors

### Lua Components

These components execute custom Lua scripts to modify the projectile's behavior.

*   **`script_source_file`**: Path to the Lua script.
*   **`execute_every_n_frame`**: How often the script is executed.
*   **`remove_after_executed`**: If `1`, the Lua component is removed after its first execution.

```xml
<LuaComponent
    script_source_file="data/scripts/projectiles/disc_bullet_bigger_trajectory.lua"
    execute_every_n_frame="3"
    >
</LuaComponent>

<LuaComponent
    script_source_file="data/scripts/projectiles/disc_bullet_big_damage.lua"
    execute_every_n_frame="8"
    remove_after_executed="1"
    >
</LuaComponent>
```

## Additional Components

### Area Damage Component

Applies damage over time to entities within a specified radius.

*   **`aabb_min` / `aabb_max`**: Defines the bounding box for the area damage.
*   **`damage_per_frame`**: The amount of damage dealt each frame.
*   **`entities_with_tag`**: Only applies damage to entities with this tag.
*   **`damage_type`**: The type of damage dealt.

```xml
<AreaDamageComponent
    _tags="area_damage"
    aabb_min.x="-15"
    aabb_min.y="-15"
    aabb_max.x="15"
    aabb_max.y="15"
    damage_per_frame="0.9"
    update_every_n_frame="1"
    entities_with_tag="hittable"
    damage_type="DAMAGE_SLICE"
    death_cause="bzzt!"
    _enabled="0"
    >
</AreaDamageComponent>
```

### Cell Eater Component

Allows the projectile to consume certain types of cells.

*   **`radius`**: The radius within which cells are consumed.
*   **`eat_probability`**: The chance (in percent) of a cell being eaten.

```xml
<CellEaterComponent
    radius="13"
    eat_probability="40"
    >
</CellEaterComponent>
```

### Variable Storage Component

Stores variables that can be accessed by other components or scripts.

*   **`name`**: The name of the variable.
*   **`value_string`**: The string value of the variable.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/disc_bullet_bigger.xml"
    >
</VariableStorageComponent>
```