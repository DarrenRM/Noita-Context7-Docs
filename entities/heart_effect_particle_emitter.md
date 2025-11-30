---
title: Heart Effect Particle Emitter
category: entities
---

# Heart Effect Particle Emitter

This entity defines a particle emitter that creates a visual "heart" effect, likely for cosmetic purposes or as a visual indicator.

## ParticleEmitterComponent

This component handles the emission of particles.

### Key Attributes:

*   **`emitted_material_name`**: `spark_red` - Specifies the material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity.
*   **`lifetime_min` / `lifetime_max`**: `8` / `15` - The duration each individual particle exists in seconds.
*   **`count_min` / `count_max`**: `8` / `8` - The number of particles emitted per emission cycle.
*   **`render_on_grid`**: `1` - Particles are rendered on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`area_circle_radius.min` / `area_circle_radius.max`**: `0` / `0` - Particles are emitted from a single point (no radius).
*   **`airflow_force`**: `0.251` - The force applied by airflow to the particles.
*   **`airflow_time`**: `1.01` - The duration airflow affects the particles.
*   **`airflow_scale`**: `0.05` - The scaling factor for airflow.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame.
*   **`emit_cosmetic_particles`**: `1` - This emitter is intended for cosmetic particles.
*   **`image_animation_file`**: `data/particles/image_emitters/heart_effect.png` - The image file used for particle animation.
*   **`image_animation_raytrace_from_center`**: `1` - Animation rays trace from the center of the image.
*   **`image_animation_speed`**: `5` - The speed of the image animation.
*   **`image_animation_loop`**: `0` - The animation does not loop.
*   **`is_emitting`**: `1` - The emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity.

### Key Attributes:

*   **`lifetime`**: `260` - The entity (and thus the emitter) exists for 260 frames.

## AudioComponent

This component plays an audio event when the entity is active.

### Key Attributes:

*   **`file`**: `data/audio/Desktop/event_cues.bank` - The audio bank containing the event.
*   **`event_root`**: `event_cues/heart` - The specific audio event to play.