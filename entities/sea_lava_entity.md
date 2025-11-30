---
title: Sea Lava Entity
category: entities
---

# Sea Lava Entity

This document describes the `sea_lava.xml` entity, which defines the behavior and appearance of sea lava in Noita.

## Entity Definition

The core entity is defined as `$projectile_default` with the tag `projectile_player`.

```xml
<Entity name="$projectile_default" tags="projectile_player" >
    <!-- Components -->
</Entity>
```

## Key Components

### MaterialSeaSpawnerComponent

This component is responsible for spawning the sea lava material.

| Attribute          | Description                                                                 |
| :----------------- | :-------------------------------------------------------------------------- |
| `size.x`           | Width of the sea lava area.                                                 |
| `size.y`           | Height of the sea lava area.                                                |
| `offset.x`         | Horizontal offset for the spawn area.                                       |
| `offset.y`         | Vertical offset for the spawn area.                                         |
| `speed`            | The speed at which the lava material is spawned or moves.                   |
| `noise_threshold`  | Threshold for noise generation, affecting the lava's texture/pattern.       |
| `material`         | The specific material to spawn (e.g., "lava").                              |

### LifetimeComponent

Determines how long the sea lava entity persists.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The duration in frames the entity exists. |

### ParticleEmitterComponent

Manages the visual particles associated with the sea lava.

| Attribute                 | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `emitted_material_name`   | The name of the material for the emitted particles (e.g., "spark").                                     |
| `gravity.y`               | Vertical gravity applied to emitted particles.                                                          |
| `lifetime_min`            | Minimum lifetime of emitted particles.                                                                  |
| `lifetime_max`            | Maximum lifetime of emitted particles.                                                                  |
| `count_min`               | Minimum number of particles emitted per emission.                                                       |
| `count_max`               | Maximum number of particles emitted per emission.                                                       |
| `render_on_grid`          | Whether particles should be rendered on the game grid.                                                  |
| `fade_based_on_lifetime`  | Whether particles fade out as their lifetime decreases.                                                 |
| `airflow_force`           | Force applied by airflow to particles.                                                                  |
| `airflow_time`            | Duration airflow affects particles.                                                                     |
| `airflow_scale`           | Scale of the airflow effect.                                                                            |
| `image_animation_file`    | Path to the image animation file for particles.                                                         |
| `image_animation_speed`   | Speed of the particle image animation.                                                                  |
| `emit_cosmetic_particles` | Whether to emit cosmetic particles (visual effects not affecting gameplay).                             |
| `is_emitting`             | Whether the particle emitter is currently active.                                                       |

### MusicEnergyAffectorComponent

This component influences energy levels, likely related to music or sound effects.

| Attribute     | Description                                     |
| :------------ | :---------------------------------------------- |
| `energy_target` | The target energy level to affect.              |

### AudioComponent

Handles the sound effects associated with the sea lava.

| Attribute           | Description                                                              |
| :------------------ | :----------------------------------------------------------------------- |
| `file`              | Path to the audio bank file.                                             |
| `event_root`        | The root event name for the audio (e.g., "player_projectiles/sea_of_lava"). |
| `set_latest_event_position` | Whether to set the audio event's position to the entity's latest position. |