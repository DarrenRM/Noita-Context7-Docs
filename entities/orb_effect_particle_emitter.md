---
title: Orb Effect Particle Emitter
category: entities
---

# Orb Effect Particle Emitter

This document describes the configuration for a particle emitter that creates an "orb effect" in Noita. It's designed to emit visual particles with specific behaviors and an associated sound cue.

## ParticleEmitterComponent

This component defines the core behavior of the particle emission.

### Key Attributes:

*   **`emitted_material_name`**: Specifies the material of the particles being emitted.
    *   Value: `"spark_blue"`
*   **`gravity.y`**: Controls the vertical gravity applied to the particles.
    *   Value: `"0.0"` (No vertical gravity)
*   **`lifetime_min` / `lifetime_max`**: The minimum and maximum lifespan of individual particles in seconds.
    *   Values: `"8"` / `"15"`
*   **`count_min` / `count_max`**: The minimum and maximum number of particles emitted per emission cycle.
    *   Values: `"8"` / `"8"`
*   **`render_on_grid`**: Determines if particles are rendered on the game grid.
    *   Value: `"1"` (Rendered)
*   **`fade_based_on_lifetime`**: If set to `1`, particles will fade out as their lifetime decreases.
    *   Value: `"1"`
*   **`area_circle_radius.min` / `area_circle_radius.max`**: Defines the radius of the circular area from which particles are emitted.
    *   Values: `"0"` / `"0"` (Emitted from a single point)
*   **`cosmetic_force_create`**: If `1`, particles are created even if the entity is not visible.
    *   Value: `"0"`
*   **`airflow_force`**: The strength of airflow affecting particles.
    *   Value: `"0.251"`
*   **`airflow_time`**: The duration airflow affects particles.
    *   Value: `"1.01"`
*   **`airflow_scale`**: The scaling factor for airflow.
    *   Value: `"0.05"`
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: The minimum and maximum frames between particle emissions.
    *   Values: `"1"` / `"1"` (Continuous emission)
*   **`emit_cosmetic_particles`**: If `1`, cosmetic particles are emitted.
    *   Value: `"1"`
*   **`image_animation_file`**: The path to the image file used for animated particles.
    *   Value: `"data/particles/image_emitters/heart_effect.png"`
*   **`image_animation_speed`**: The speed of the image animation.
    *   Value: `"5"`
*   **`image_animation_loop`**: Whether the image animation should loop.
    *   Value: `"0"` (Does not loop)
*   **`image_animation_raytrace_from_center`**: If `1`, raytracing for animation starts from the center of the image.
    *   Value: `"1"`
*   **`is_emitting`**: Controls whether the emitter is currently active.
    *   Value: `"1"` (Emitting)

## LifetimeComponent

This component defines the overall lifespan of the entity that hosts the particle emitter.

### Key Attributes:

*   **`lifetime`**: The total lifespan of the entity in seconds.
    *   Value: `"260"`

## AudioComponent

This component associates a sound event with the entity.

### Key Attributes:

*   **`file`**: The path to the audio bank file.
    *   Value: `"data/audio/Desktop/event_cues.bank"`
*   **`event_root`**: The root event name within the audio bank.
    *   Value: `"event_cues/orb"`