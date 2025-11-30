---
title: Alcohol Mist Projectile
category: entities
---

# Alcohol Mist Projectile

This document describes the configuration for the "Alcohol Mist" projectile entity in Noita, focusing on its key attributes for AI-assisted modding.

## Entity Definition

The core entity is defined as a projectile, tagged for player use.

```xml
<Entity tags="" name="$projectile_default" tags="projectile_player,projectile" >
    <!-- ... components ... -->
</Entity>
```

## Key Components

### Velocity Component

This component defines the projectile's movement characteristics.

*   **`gravity_y="0"`**: No vertical gravity applied.
*   **`air_friction="0"`**: No air resistance.
*   **`mass="0.00"`**: Negligible mass.

```xml
<VelocityComponent
    gravity_y="0"
    air_friction="0"
    mass="0.00"
    >
</VelocityComponent>
```

### Particle Emitter Component

This component is responsible for emitting particles that form the mist effect.

*   **`emitted_material_name="alcohol_gas"`**: The material of the particles emitted.
*   **`count_min="1"`, `count_max="3"`**: The number of particles emitted per emission.
*   **`emission_interval_min_frames="10"`, `emission_interval_max_frames="10"`**: The interval between particle emissions in frames.
*   **`image_animation_file="data/particles/image_emitters/cloud_circle.png"`**: The sprite used for the emitted particles.
*   **`create_real_particles="1"`**: Ensures actual particles are created, not just cosmetic ones.

```xml
<ParticleEmitterComponent
    emitted_material_name="alcohol_gas"
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
    count_max="3"
    emission_interval_min_frames="10"
    emission_interval_max_frames="10"
    image_animation_file="data/particles/image_emitters/cloud_circle.png"
    image_animation_loop="1"
    emit_cosmetic_particles="0"
    create_real_particles="1" >
</ParticleEmitterComponent>
```

### Projectile Component

This component governs the behavior of the projectile itself.

*   **`damage="0"`**: The projectile itself deals no damage.
*   **`lifetime="100"`**: The projectile exists for 100 frames.
*   **`damage_every_x_frames="25"`**: While damage is 0, this indicates a potential for damage application if it were present.
*   **`on_collision_die="0"`**: The projectile does not die upon collision.
*   **`die_on_low_velocity="0"`**: The projectile does not die due to low velocity.
*   **`on_death_explode="0"`**: No explosion occurs when the projectile dies.

The `config_explosion` within this component is largely disabled for this projectile, indicating no explosive effects.

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
    lifetime="100"
    knockback_force="0"
    damage_every_x_frames="25"
    >
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
</ProjectileComponent>
```

### Audio Components

These components handle the sound effects associated with the projectile.

*   **`AudioComponent`**: Plays an initial sound event upon projectile creation.
    *   `file="data/audio/Desktop/projectiles.bank"`
    *   `event_root="player_projectiles/mist"`
*   **`AudioLoopComponent`**: Plays a looping sound effect.
    *   `file="data/audio/Desktop/projectiles.bank"`
    *   `event_name="player_projectiles/mist/loop"`
    *   `auto_play="1"`

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/mist">
</AudioComponent>

<AudioLoopComponent
    file="data/audio/Desktop/projectiles.bank"
    event_name="player_projectiles/mist/loop"
    auto_play="1">
</AudioLoopComponent>
```