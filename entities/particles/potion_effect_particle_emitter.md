---
title: Potion Effect Particle Emitter
category: entities/particles
---

# Potion Effect Particle Emitter

This entity defines a particle emitter that creates visual effects for potion effects, specifically by converting a material over time and emitting animated particles.

## Key Components

### ParticleEmitterComponent

This component controls the emission of particles.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `emitted_material_name`   | The material of the particles to be emitted (e.g., `plasma_fading_pink`).   |
| `gravity.y`               | Vertical gravity applied to particles. `0.0` means no gravity.              |
| `lifetime_min`, `lifetime_max` | Minimum and maximum lifetime of individual particles in seconds.              |
| `count_min`, `count_max`  | Minimum and maximum number of particles emitted per emission.               |
| `fade_based_on_lifetime`  | If `1`, particles fade out as their lifetime decreases.                     |
| `airflow_force`           | The strength of airflow affecting particles.                                |
| `emission_interval_min_frames`, `emission_interval_max_frames` | Controls how often particles are emitted in frames. `1` means continuous emission. |
| `emit_cosmetic_particles` | If `1`, emits particles that are purely cosmetic and don't interact physically. |
| `image_animation_file`    | Path to the image file used for animating the particles.                    |
| `image_animation_speed`   | Speed of the image animation.                                               |
| `image_animation_loop`    | If `0`, the animation plays once. If `1`, it loops.                         |
| `is_emitting`             | If `1`, the emitter is active.                                              |

### LifetimeComponent

Determines the overall lifetime of the entity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `lifetime`| The total lifetime of the entity in seconds. |

### MagicConvertMaterialComponent

This component allows the entity to convert one material into another over time within a specified radius.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `kill_when_finished` | If `0`, the entity persists after conversion. If `1`, it is destroyed. |
| `from_material` | The material to be converted (e.g., `glowstone_potion`).                 |
| `to_material` | The material to convert into (e.g., `blood`).                            |
| `radius`      | The radius within which the material conversion occurs.                  |

### AudioComponent

Handles the audio associated with the entity.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `file`      | The audio bank file containing the sound events.                         |
| `event_root`| The root event name for the potion-related audio cues.                   |