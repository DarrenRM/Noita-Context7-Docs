---
title: Bloomshot Projectile
category: entities
---

# Bloomshot Projectile

This document details the `bloomshot.xml` entity, a projectile in Noita. It's designed to be a small, fast-moving projectile that explodes on impact or after a short duration, leaving behind acid gas and a stain.

## Key Components and Attributes

### ProjectileComponent

This component defines the core behavior of the projectile.

| Attribute           | Value      | Description                                                                 |
| :------------------ | :--------- | :-------------------------------------------------------------------------- |
| `speed_min`         | `90`       | Minimum projectile speed.                                                   |
| `speed_max`         | `90`       | Maximum projectile speed.                                                   |
| `die_on_low_velocity` | `0`        | Projectile does not die if its velocity drops too low.                      |
| `on_death_explode`  | `1`        | Projectile explodes when it dies (e.g., on collision or lifetime out).      |
| `on_lifetime_out_explode` | `1`        | Projectile explodes when its lifetime expires.                              |
| `on_collision_die`  | `1`        | Projectile dies upon collision with an entity.                              |
| `damage`            | `0.26`     | Base damage dealt by the projectile.                                        |
| `lifetime`          | `120`      | Duration in frames before the projectile explodes if it hasn't collided.    |
| `knockback_force`   | `1.0`      | Force applied to entities upon collision.                                   |

### Config Explosion

This nested component within `ProjectileComponent` defines the properties of the explosion that occurs when the projectile dies.

| Attribute                 | Value                               | Description                                                                                             |
| :------------------------ | :---------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `damage`                  | `0.2`                               | Damage dealt by the explosion.                                                                          |
| `camera_shake`            | `3.5`                               | Intensity of camera shake upon explosion.                                                               |
| `explosion_radius`        | `12`                                | Radius of the explosion's effect.                                                                       |
| `explosion_sprite`        | `data/particles/explosion_032_slimeburst.xml` | Path to the sprite used for the explosion visual effect.                                                |
| `create_cell_material`    | `acid_gas`                          | Material created in the world at the explosion's location.                                              |
| `create_cell_probability` | `40`                                | Percentage chance (out of 100) that `create_cell_material` will be spawned.                             |
| `hole_enabled`            | `1`                                 | Whether the explosion creates a hole in the terrain.                                                    |
| `hole_image`              | `data/temp/explosion_hole.png`      | Image used for the explosion hole.                                                                      |
| `physics_explosion_power` | `min="0.4" max="0.6"`               | Minimum and maximum power of the physics-based explosion, affecting nearby objects.                     |
| `shake_vegetation`        | `1`                                 | Whether the explosion shakes vegetation.                                                                |
| `stains_enabled`          | `1`                                 | Whether the explosion leaves stains on the ground.                                                      |
| `stains_radius`           | `9`                                 | Radius of the stains left by the explosion.                                                             |
| `audio_event_name`        | `explosions/slime_small`            | Name of the audio event to play upon explosion.                                                         |

### SpriteComponent

Defines the visual representation of the projectile.

| Attribute     | Value                               | Description                                                               |
| :------------ | :---------------------------------- | :------------------------------------------------------------------------ |
| `image_file`  | `data/projectiles_gfx/slimeball_small.xml` | Path to the sprite file for the projectile.                               |
| `alpha`       | `1`                                 | Opacity of the sprite (1 is fully opaque).                                |
| `offset_x`    | `0`                                 | Horizontal offset of the sprite.                                          |
| `offset_y`    | `0`                                 | Vertical offset of the sprite.                                            |

### ParticleEmitterComponent

Responsible for generating cosmetic particles around the projectile.

| Attribute                 | Value   | Description                                                                                             |
| :------------------------ | :------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | `acid`  | The material of the particles to be emitted.                                                            |
| `count_min`               | `1`     | Minimum number of particles emitted per emission cycle.                                                 |
| `count_max`               | `2`     | Maximum number of particles emitted per emission cycle.                                                 |
| `offset.x`                | `0`     | Horizontal offset for particle emission.                                                                |
| `offset.y`                | `5`     | Vertical offset for particle emission.                                                                  |
| `x_vel_min`               | `-50`   | Minimum horizontal velocity of emitted particles.                                                       |
| `x_vel_max`               | `50`    | Maximum horizontal velocity of emitted particles.                                                       |
| `y_vel_min`               | `-50`   | Minimum vertical velocity of emitted particles.                                                         |
| `y_vel_max`               | `50`    | Maximum vertical velocity of emitted particles.                                                         |
| `lifetime_min`            | `0.1`   | Minimum lifetime in seconds for emitted particles.                                                      |
| `lifetime_max`            | `0.3`   | Maximum lifetime in seconds for emitted particles.                                                      |
| `emission_interval_min_frames` | `5`     | Minimum frames between particle emission cycles.                                                        |
| `emission_interval_max_frames` | `8`     | Maximum frames between particle emission cycles.                                                        |
| `is_emitting`             | `1`     | Whether the particle emitter is currently active.                                                       |

### AudioComponent

Defines the sound effects associated with the projectile.

| Attribute      | Value                               | Description                                                               |
| :------------- | :---------------------------------- | :------------------------------------------------------------------------ |
| `file`         | `data/audio/Desktop/projectiles.bank` | Path to the audio bank containing the sound events.                       |
| `event_root`   | `projectiles/bloomshot`             | The root event name for projectile sounds.                                |

### VariableStorageComponent

Stores variables associated with the entity.

| Attribute    | Value                               | Description                                                               |
| :----------- | :---------------------------------- | :------------------------------------------------------------------------ |
| `name`       | `projectile_file`                   | The name of the variable.                                                 |
| `value_string` | `data/entities/projectiles/bloomshot.xml` | The string value of the variable, pointing to this entity's file.         |