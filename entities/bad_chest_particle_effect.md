---
title: Bad Chest Particle Effect
category: entities
---

# Bad Chest Particle Effect

This entity defines the visual and auditory effects that play when a "bad" chest is opened in Noita. It primarily uses a `ParticleEmitterComponent` to generate red sparks with a specific image animation.

## Key Components

### `LifetimeComponent`

*   **lifetime**: `260` - The duration in frames for which this entity will exist.

### `AudioComponent`

*   **file**: `data/audio/Desktop/event_cues.bank` - The audio bank containing the sound effect.
*   **event_root**: `event_cues/chest_bad` - The specific event cue to trigger for the "bad" chest sound.
*   **play_only_if_visible**: `1` - Ensures the sound only plays if the effect is currently on-screen.

### `ParticleEmitterComponent`

This is the core component responsible for generating the visual particles.

*   **emitted_material_name**: `spark_red` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - No vertical gravity applied to the particles.
*   **lifetime_min**: `8` - Minimum lifetime in frames for each emitted particle.
*   **lifetime_max**: `15` - Maximum lifetime in frames for each emitted particle.
*   **count_min**: `15` - Minimum number of particles emitted per emission cycle.
*   **count_max**: `15` - Maximum number of particles emitted per emission cycle.
*   **render_on_grid**: `1` - Particles will be rendered even on the game grid.
*   **fade_based_on_lifetime**: `1` - Particles will fade out as their lifetime decreases.
*   **area_circle_radius.min**: `0` - Minimum radius of the emission area (a single point).
*   **area_circle_radius.max**: `0` - Maximum radius of the emission area (a single point).
*   **cosmetic_force_create**: `0` - Not a cosmetic-only particle effect.
*   **airflow_force**: `1.551` - The strength of airflow affecting the particles.
*   **airflow_time**: `1.01` - The duration airflow affects the particles.
*   **airflow_scale**: `0.05` - The scaling factor for airflow.
*   **emission_interval_min_frames**: `1` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `1` - Maximum frames between particle emissions.
*   **emit_cosmetic_particles**: `1` - Emits cosmetic particles.
*   **image_animation_file**: `data/particles/image_emitters/chest_effect.png` - The image file used for particle animation.
*   **image_animation_speed**: `15` - The speed of the image animation in frames per second.
*   **image_animation_loop**: `0` - The animation does not loop.
*   **is_emitting**: `1` - The emitter is active and will emit particles.