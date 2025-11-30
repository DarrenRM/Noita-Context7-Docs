---
title: Small Acid Circle Projectile
category: entities
---

# Small Acid Circle Projectile

This document describes the configuration for a small acid projectile entity in Noita, designed for AI-assisted modding.

## Core Entity Configuration

The projectile is defined as a player projectile with the tag `projectile_player`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  <!-- ... components ... -->
</Entity>
```

## Key Components

### ParticleEmitterComponent

This component governs the visual and physical particle effects associated with the projectile.

| Attribute                 | Value        | Description                                                                 |
| :------------------------ | :----------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `acid`       | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`          | Indicates that actual game particles should be created.                     |
| `gravity.y`               | `0.0`        | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`          | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`         | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`          | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`          | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`          | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`          | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `0.251`      | The force applied by airflow to the particles.                              |
| `airflow_time`            | `1.01`       | Duration for which airflow affects particles.                               |
| `airflow_scale`           | `0.05`       | Scaling factor for airflow's effect.                                        |
| `image_animation_file`    | `data/particles/image_emitters/circle_256.png` | The sprite sheet used for particle animation. |
| `image_animation_speed`   | `1`          | Speed of the particle animation.                                            |
| `set_magic_creation`      | `1`          | Marks this as a magic-created particle.                                     |
| `is_emitting`             | `1`          | The particle emitter is active.                                             |

### LifetimeComponent

This component defines the total lifespan of the projectile itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `120` | The projectile exists for 120 frames.     |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute    | Value                               | Description                                     |
| :----------- | :---------------------------------- | :---------------------------------------------- |
| `file`       | `data/audio/Desktop/projectiles.bank` | The audio bank containing projectile sounds.    |
| `event_root` | `player_projectiles/circle_of`      | The root event name for player projectile sounds. |