---
title: Chest Effect Particle Emitter
category: entities/particles
---

# Chest Effect Particle Emitter

This entity defines the visual and auditory effects that play when a chest is opened in Noita. It primarily uses a `ParticleEmitterComponent` to generate cosmetic sparks.

## Key Components

### `LifetimeComponent`

*   **lifetime**: `260` - The duration for which this entity (and its effects) will persist.

### `AudioComponent`

*   **file**: `data/audio/Desktop/event_cues.bank` - Specifies the audio bank containing the sound effects.
*   **event_root**: `event_cues/chest` - The root event name within the audio bank to trigger for chest-related sounds.
*   **play_only_if_visible**: `1` - Ensures the sound only plays if the chest is currently on screen.

### `ParticleEmitterComponent`

This is the core component responsible for generating the visual "spark" effect.

*   **emitted_material_name**: `spark_yellow` - The material used for the emitted particles.
*   **gravity.y**: `0.0` - Particles have no vertical gravity, allowing them to float or be affected by other forces.
*   **lifetime_min**: `8` - Minimum duration each individual spark particle will exist.
*   **lifetime_max**: `15` - Maximum duration each individual spark particle will exist.
*   **count_min**: `15` - Minimum number of particles emitted per emission cycle.
*   **count_max**: `15` - Maximum number of particles emitted per emission cycle.
*   **render_on_grid**: `1` - Particles are rendered even when the game is paused or in certain UI states.
*   **fade_based_on_lifetime**: `1` - Particles will fade out as their lifetime approaches zero.
*   **area_circle_radius.min**: `0` - The minimum radius of the emission area (a point source).
*   **area_circle_radius.max**: `0` - The maximum radius of the emission area (a point source).
*   **airflow_force**: `1.551` - The strength of airflow affecting the particles.
*   **airflow_time**: `1.01` - The duration for which airflow affects particles.
*   **airflow_scale**: `0.05` - The scaling factor for airflow effects.
*   **emission_interval_min_frames**: `1` - Minimum frames between particle emissions.
*   **emission_interval_max_frames**: `1` - Maximum frames between particle emissions (effectively continuous emission).
*   **emit_cosmetic_particles**: `1` - Indicates these are purely visual effects.
*   **image_animation_file**: `data/particles/image_emitters/chest_effect.png` - The image file used for particle animation.
*   **image_animation_speed**: `15` - The speed of the image animation in frames per second.
*   **image_animation_loop**: `0` - The animation will not loop.
*   **is_emitting**: `1` - The emitter is active and will produce particles.