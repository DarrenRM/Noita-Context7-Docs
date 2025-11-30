---
title: Grenade Projectile
category: entities
---

# Grenade Projectile

This document details the configuration of the "Grenade" projectile entity in Noita, focusing on key attributes relevant to AI-assisted modding.

## Entity Definition

The core of the grenade projectile is defined by its `Entity` tag, which includes the name and player-related tags.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... other components ... -->
</Entity>
```

## Projectile Component

This is the most crucial component, defining the projectile's behavior, physics, and effects.

### Key Attributes:

| Attribute                 | Description                                                                 | Value Example |
| :------------------------ | :-------------------------------------------------------------------------- | :------------ |
| `lob_min`, `lob_max`      | Minimum and maximum lob angle (in radians) for projectile trajectory.       | `0.9`, `1.0`  |
| `speed_min`, `speed_max`  | Minimum and maximum initial speed of the projectile.                        | `250`, `280`  |
| `friction`                | Friction applied to the projectile, affecting its deceleration.             | `0.6`         |
| `direction_random_rad`    | Randomness added to the projectile's initial direction in radians.          | `0.05`        |
| `on_death_explode`        | Whether the projectile explodes upon death (e.g., hitting a surface).       | `1`           |
| `on_lifetime_out_explode` | Whether the projectile explodes when its lifetime expires.                  | `1`           |
| `on_collision_die`        | Whether the projectile dies upon collision with an entity.                  | `1`           |
| `lifetime`                | Base lifetime of the projectile in frames.                                  | `500`         |
| `lifetime_randomness`     | Randomness added to the projectile's lifetime.                              | `7`           |
| `damage`                  | Base damage dealt by the projectile.                                        | `1.3`         |
| `bounces_left`            | Number of bounces the projectile can perform before dying.                  | `4`           |
| `knockback_force`         | Force applied to entities upon collision.                                   | `1.0`         |
| `physics_impulse_coeff`   | Coefficient for physics impulse, affecting how it interacts with physics.   | `3000`        |

### Damage by Type:

Allows specifying damage multipliers for different damage types.

```xml
<damage_by_type
    fire="0.5"
    >
</damage_by_type>
```

### Config Explosion:

Defines the properties of the explosion that occurs when `on_death_explode` or `on_lifetime_out_explode` is true.

| Attribute               | Description                                                               | Value Example |
| :---------------------- | :------------------------------------------------------------------------ | :------------ |
| `camera_shake`          | Intensity of camera shake during the explosion.                           | `10`          |
| `explosion_radius`      | The radius of the explosion's effect.                                     | `7`           |
| `explosion_sprite`      | Path to the sprite used for the explosion visual.                         | `data/particles/explosion_016.xml` |
| `load_this_entity`      | Entity to load upon explosion (e.g., for secondary effects).              | `data/entities/particles/particle_explosion/main_gunpowder_tiny.xml` |
| `hole_enabled`          | Whether the explosion creates holes in terrain.                           | `1`           |
| `ray_energy`            | Energy of the explosion's destructive rays.                               | `350000`      |
| `damage`                | Damage dealt by the explosion itself.                                     | `1.9`         |
| `physics_explosion_power.min`, `.max` | Minimum and maximum power of the physics-based explosion force. | `0.3`, `0.6`  |
| `physics_throw_enabled` | Whether the explosion applies physics impulse to nearby objects.            | `1`           |
| `audio_event_name`      | Name of the audio event to play for the explosion.                        | `explosions/magic_grenade_tiny` |

## Sprite Component

Defines the visual representation of the grenade.

```xml
<SpriteComponent
    _enabled="1"
    alpha="1"
    image_file="data/projectiles_gfx/grenade.xml"
    offset_x="4"
    offset_y="4"
    additive="1"
     >
</SpriteComponent>
```

## Particle Emitter Components

These components define various particle effects associated with the grenade.

### Smoke Emitter:

Emits smoke particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="smoke"
    x_vel_min="-2"
    x_vel_max="2"
    y_vel_min="-5"
    y_vel_max="0"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.4"
    create_real_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="3"
    is_emitting="1"
    >
</ParticleEmitterComponent>
```

### Fire Emitter:

Emits fire particles.

```xml
<ParticleEmitterComponent
    emitted_material_name="fire"
    x_vel_min="-2"
    x_vel_max="2"
    y_vel_min="-5"
    y_vel_max="0"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.4"
    create_real_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="3"
    is_emitting="1" >
</ParticleEmitterComponent>
```

### Cosmetic Spark Emitter (Initial):

Emits cosmetic sparks upon firing.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark"
    x_vel_min="-20"
    x_vel_max="20"
    y_vel_min="-20"
    y_vel_max="20"
    count_min="1"
    count_max="1"
    lifetime_min="0.1"
    lifetime_max="0.3"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    gravity.y="300"
    is_emitting="1" >
</ParticleEmitterComponent>
```

### Trail Spark Emitter:

Emits sparks as a trail behind the projectile.

```xml
<ParticleEmitterComponent
    emitted_material_name="spark"
    count_min="1"
    count_max="8"
    gravity.y="-10"
    lifetime_min="0.5"
    lifetime_max="0.8"
    airflow_force="1.2"
    airflow_time="0.1"
    airflow_scale="0.03"
    is_trail="1"
    trail_gap="0.5"
    render_on_grid="1"
    fade_based_on_lifetime="1"
    create_real_particles="0"
    emit_cosmetic_particles="1"
    emission_interval_min_frames="1"
    emission_interval_max_frames="1"
    is_emitting="1"
    >
</ParticleEmitterComponent>
```

## Audio Component

Defines the sound effects associated with the projectile.

```xml
<AudioComponent
    file="data/audio/Desktop/projectiles.bank"
    event_root="player_projectiles/bullet_launcher">
</AudioComponent>
```

## Light Component

Defines the light emitted by the projectile.

```xml
<LightComponent
    _enabled="1"
    radius="60"
    r="120"
    g="80"
    b="10">
</LightComponent>
```

## Variable Storage Component

Stores variables related to the projectile, such as its own file path.

```xml
<VariableStorageComponent
    name="projectile_file"
    value_string="data/entities/projectiles/deck/grenade.xml"
    >
</VariableStorageComponent>
```