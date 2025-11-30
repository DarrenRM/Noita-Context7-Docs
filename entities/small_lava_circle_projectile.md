---
title: Small Lava Circle Projectile
category: entities
---

# Small Lava Circle Projectile

This document describes the configuration for a small lava circle projectile in Noita, intended for AI-assisted modding.

## Entity Configuration

The core entity is defined as a player projectile.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
  ...
</Entity>
```

## Key Components

### ParticleEmitterComponent

This component controls the visual and physical particle effects of the projectile.

| Attribute                 | Value      | Description                                                                 |
| :------------------------ | :--------- | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `lava`     | The material of the particles being emitted.                                |
| `create_real_particles`   | `1`        | Indicates that actual game particles should be created.                     |
| `gravity.y`               | `0.0`      | No vertical gravity applied to the emitted particles.                       |
| `lifetime_min`            | `8`        | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `15`       | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `1`        | Minimum number of particles emitted per emission.                           |
| `count_max`               | `1`        | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`        | Particles are rendered on the game grid.                                    |
| `fade_based_on_lifetime`  | `1`        | Particles fade out as their lifetime decreases.                             |
| `airflow_force`           | `0.251`    | Force applied by airflow to the particles.                                  |
| `airflow_time`            | `1.01`     | Duration of airflow influence on particles.                                 |
| `airflow_scale`           | `0.05`     | Scale of the airflow effect.                                                |
| `image_animation_file`    | `...circle_256.png` | Texture file for particle animation.                                        |
| `set_magic_creation`      | `1`        | Marks this as a magic-related creation.                                     |
| `is_emitting`             | `1`        | The particle emitter is active.                                             |

### AudioComponent

This component handles the sound effects associated with the projectile.

| Attribute      | Value                               | Description                                     |
| :------------- | :---------------------------------- | :---------------------------------------------- |
| `file`         | `data/audio/Desktop/projectiles.bank` | The audio bank file containing the sound events. |
| `event_root`   | `player_projectiles/sea_of_lava`    | The specific sound event to trigger.            |

### LifetimeComponent

This component defines the total lifespan of the projectile itself.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `120` | The projectile will exist for 120 frames. |