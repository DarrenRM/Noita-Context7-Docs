---
title: Mist Blood Projectile
category: entities
---

# Mist Blood Projectile

This document details the configuration of the "Mist Blood" projectile entity in Noita, focusing on its behavior and visual/audio components.

## Entity Definition

The core entity is defined as a projectile, primarily for player use.

```xml
<Entity tags="" name="$projectile_default" tags="projectile_player,projectile" >
    <!-- ... components ... -->
</Entity>
```

## Key Components

### Velocity Component

This component defines the projectile's movement characteristics.

| Attribute       | Value   | Description                                  |
| :-------------- | :------ | :------------------------------------------- |
| `gravity_y`     | `0`     | No vertical gravity applied.                 |
| `air_friction`  | `0`     | No air resistance.                           |
| `mass`          | `0.00`  | Negligible mass, affecting physics minimally. |

### Particle Emitter Component

This component governs the visual effect of the projectile, emitting "cloud_blood" particles.

| Attribute                   | Value                                       | Description                                                              |
| :-------------------------- | :------------------------------------------ | :----------------------------------------------------------------------- |
| `emitted_material_name`     | `cloud_blood`                               | The material of the particles to be emitted.                             |
| `count_min` / `count_max`   | `1` / `10`                                  | The range of particles emitted per emission cycle.                       |
| `emission_interval_min_frames` / `emission_interval_max_frames` | `6` / `6` | Particles are emitted every 6 frames.                                    |
| `image_animation_file`      | `data/particles/image_emitters/cloud_circle.png` | The sprite sheet used for animating the emitted particles.               |
| `create_real_particles`     | `1`                                         | Ensures that actual particles are created, not just cosmetic effects.    |

### Projectile Component

This component defines the projectile's core behavior, including its damage, lifetime, and collision properties.

| Attribute               | Value   | Description                                                              |
| :---------------------- | :------ | :----------------------------------------------------------------------- |
| `damage`                | `0`     | The projectile deals no direct damage.                                   |
| `lifetime`              | `500`   | The projectile exists for 500 frames before despawning.                  |
| `damage_every_x_frames` | `25`    | If damage were applied, it would occur every 25 frames. (Not applicable here) |
| `on_collision_die`      | `0`     | The projectile does not die upon collision.                              |
| `die_on_low_velocity`   | `0`     | The projectile does not despawn due to low velocity.                     |
| `on_death_explode`      | `0`     | The projectile does not explode upon death.                              |

#### Config Explosion

This nested configuration defines explosion properties, which are largely disabled for this projectile.

| Attribute             | Value   | Description                                  |
| :-------------------- | :------ | :------------------------------------------- |
| `explosion_radius`    | `0`     | No explosion radius.                         |
| `damage_mortals`      | `0`     | No damage to mortals from any potential explosion. |
| `hole_enabled`        | `0`     | No terrain destruction.                      |
| `particle_effect`     | `0`     | No explosion particle effects.               |

### Audio Component & Audio Loop Component

These components handle the sound effects associated with the projectile.

| Attribute     | Value                                   | Description                                                              |
| :------------ | :-------------------------------------- | :----------------------------------------------------------------------- |
| `file`        | `data/audio/Desktop/projectiles.bank`   | The audio bank containing the sound events.                              |
| `event_root`  | `player_projectiles/mist`               | The base event name for the projectile's sounds.                         |
| `event_name`  | `player_projectiles/mist/loop`          | The specific event name for the looping sound effect.                    |
| `auto_play`   | `1`                                     | The looping sound effect starts automatically when the projectile is active. |