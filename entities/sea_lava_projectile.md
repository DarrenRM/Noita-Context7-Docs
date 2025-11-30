---
title: Sea Lava Projectile
category: entities
---

# Sea Lava Projectile

This entity defines the "Sea of Lava" projectile used in Noita. It's characterized by its large area of effect, continuous spawning of lava material, and associated particle effects and audio.

## Key Components

### MaterialSeaSpawnerComponent

This component is responsible for spawning the "lava" material over a defined area.

| Attribute           | Value   | Description                                                                 |
| :------------------ | :------ | :-------------------------------------------------------------------------- |
| `size.x`            | `300`   | Width of the area where lava is spawned.                                    |
| `size.y`            | `256`   | Height of the area where lava is spawned.                                   |
| `offset.x`          | `0`     | Horizontal offset for the spawn area.                                       |
| `offset.y`          | `158`   | Vertical offset for the spawn area.                                         |
| `speed`             | `10`    | Speed at which the lava material is spawned or moves.                       |
| `noise_threshold`   | `0.0`   | Threshold for noise generation, affecting spawn patterns.                   |
| `material`          | `lava`  | The material to be spawned.                                                 |

### LifetimeComponent

Determines how long the projectile (and its effects) will persist.

| Attribute | Value | Description                               |
| :-------- | :---- | :---------------------------------------- |
| `lifetime`| `300` | Duration in frames before the entity despawns. |

### ParticleEmitterComponent

Manages the emission of cosmetic particles, such as sparks, to enhance the visual effect.

| Attribute                 | Value   | Description                                                                 |
| :------------------------ | :------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | `spark` | The name of the material for the emitted particles.                         |
| `gravity.y`               | `0.0`   | Vertical gravity applied to emitted particles.                              |
| `lifetime_min`            | `6`     | Minimum lifetime of emitted particles in frames.                            |
| `lifetime_max`            | `8`     | Maximum lifetime of emitted particles in frames.                            |
| `count_min`               | `8`     | Minimum number of particles emitted per emission.                           |
| `count_max`               | `8`     | Maximum number of particles emitted per emission.                           |
| `render_on_grid`          | `1`     | Whether particles should be rendered on the game grid.                      |
| `fade_based_on_lifetime`  | `1`     | Whether particles fade out as their lifetime decreases.                     |
| `airflow_force`           | `0.51`  | Force applied by airflow to the particles.                                  |
| `image_animation_file`    | `data/particles/image_emitters/sea_lava.png` | Path to the sprite sheet for particle animation. |
| `image_animation_speed`   | `5`     | Speed of the particle animation.                                            |
| `is_emitting`             | `1`     | Whether the particle emitter is active.                                     |

### AudioComponent

Handles the sound effects associated with the Sea of Lava projectile.

| Attribute        | Value                                | Description                                                              |
| :--------------- | :----------------------------------- | :----------------------------------------------------------------------- |
| `file`           | `data/audio/Desktop/projectiles.bank`| The audio bank file containing the sound events.                         |
| `event_root`     | `player_projectiles/sea_of_lava`     | The root event name for the projectile's sounds.                         |
| `set_latest_event_position` | `1` | Ensures the sound plays at the projectile's current position. |

## Other Components

*   **`MusicEnergyAffectorComponent`**: This component influences the game's music energy, setting the target to `1.0`. This likely means it contributes to a high-energy state in the music.