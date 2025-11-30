---
title: Mist Slime Projectile
category: entities
---

# Mist Slime Projectile

This document details the configuration for the "Mist Slime" projectile entity in Noita, focusing on its behavior and visual/audio components.

## Core Entity Configuration

The `Entity` tag defines the base object.

```xml
<Entity tags="" name="$projectile_default" tags="projectile_player,projectile" >
    <!-- ... components ... -->
</Entity>
```

*   **`name`**: `$projectile_default` - Indicates this is a default projectile type.
*   **`tags`**: `projectile_player,projectile` - Identifies it as a player-made projectile.

## Velocity Component

Controls the projectile's movement physics.

```xml
<VelocityComponent
    gravity_y="0"
    air_friction="0"
    mass="0.00"
    >
</VelocityComponent>
```

*   **`gravity_y`**: `0` - No vertical gravity applied.
*   **`air_friction`**: `0` - No air resistance.
*   **`mass`**: `0.00` - Negligible mass, contributing to its floaty nature.

## Particle Emitter Component

Responsible for generating visual particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="cloud_slime"
    offset.x="0"
    offset.y="0"
    x_pos_offset_min="0"
    x_pos_offset_max="0"
    y_pos_offset_min="0"
    y_pos_offset_max="0"
    x_vel_min="0"
    x_vel_max="0"
    y_vel_min="0"
    y_vel_max="0"
    count_min="1"
    count_max="10"
    emission_interval_min_frames="6"
    emission_interval_max_frames="6"
    image_animation_file="data/particles/image_emitters/cloud_circle.png"
    image_animation_loop="1"
    emit_cosmetic_particles="0"
    create_real_particles="1" >
</ParticleEmitterComponent>
```

*   **`emitted_material_name`**: `cloud_slime` - The material used for the emitted particles.
*   **`count_min`/`count_max`**: `1`/`10` - The number of particles emitted per interval.
*   **`emission_interval_min_frames`/`emission_interval_max_frames`**: `6`/`6` - Particles are emitted every 6 frames.
*   **`image_animation_file`**: `data/particles/image_emitters/cloud_circle.png` - The sprite sheet for the particle animation.
*   **`create_real_particles`**: `1` - Ensures these are actual game particles, not just cosmetic effects.

## Projectile Component

Defines the projectile's core behavior and properties.

```xml
<ProjectileComponent
    _enabled="1"
    lob_min="0.1"
    lob_max="1.0"
    speed_min="0"
    speed_max="0"
    die_on_low_velocity="0"
    on_death_explode="0"
    on_death_gfx_leave_sprite="0"
    on_lifetime_out_explode="0"
    explosion_dont_damage_shooter="1"
    damage="0"
    on_collision_die="0"
    lifetime="500"
    knockback_force="0"
    damage_every_x_frames="25"
    >
    <!-- ... config_explosion ... -->
</ProjectileComponent>
```

*   **`lob_min`/`lob_max`**: `0.1`/`1.0` - Controls the arc of the projectile.
*   **`speed_min`/`speed_max`**: `0`/`0` - The projectile has no initial speed.
*   **`die_on_low_velocity`**: `0` - Does not die if its velocity drops.
*   **`on_death_explode`**: `0` - Does not explode upon death.
*   **`on_lifetime_out_explode`**: `0` - Does not explode when its lifetime ends.
*   **`damage`**: `0` - Deals no direct damage.
*   **`on_collision_die`**: `0` - Does not die upon collision.
*   **`lifetime`**: `500` - The projectile exists for 500 frames.
*   **`damage_every_x_frames`**: `25` - If damage were applied, it would be every 25 frames.

### Projectile Explosion Configuration

This nested tag defines explosion properties, though most are disabled for this projectile.

```xml
<config_explosion
    never_cache="1"
    camera_shake="0"
    explosion_radius="0"
    explosion_sprite=""
    explosion_sprite_lifetime="0.0"
    create_cell_probability="0"
    create_cell_material=""
    ray_energy="0"
    hole_enabled="0"
    particle_effect="0"
    damage_mortals="0"
    physics_throw_enabled="0"
    shake_vegetation="0"
    sparks_enabled="0"
    light_fade_time="0.1"
    stains_enabled="0"
    >
</config_explosion>
```

*   Most attributes are set to `0` or empty, indicating no explosion effects are triggered.

## Audio Component

Handles the initial sound effect when the projectile is fired.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/mist">
</AudioComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank containing the sound.
*   **`event_root`**: `player_projectiles/mist` - The specific sound event for this projectile.

## Audio Loop Component

Manages a looping sound effect for the projectile.

```xml
<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/mist/loop"
    auto_play="1">
</AudioLoopComponent>
```

*   **`file`**: `data/audio/Desktop/projectiles.bank` - The audio bank.
*   **`event_name`**: `player_projectiles/mist/loop` - The name of the looping sound event.
*   **`auto_play`**: `1` - The loop starts automatically when the projectile is created.