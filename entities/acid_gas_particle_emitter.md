---
title: Acid Gas Particle Emitter
category: entities
---

# Acid Gas Particle Emitter

This entity defines a particle emitter that generates "acid gas" particles. It's designed to create a visual effect of gas with specific properties.

## ParticleEmitterComponent

This is the core component responsible for emitting particles.

### Key Attributes:

*   **`emitted_material_name`**: `"acid_gas"` - Specifies the material of the particles being emitted.
*   **`create_real_particles`**: `"1"` - Indicates that actual game particles should be created, not just cosmetic ones.
*   **`gravity.y`**: `"0.0"` - Particles have no vertical gravity, meaning they won't fall.
*   **`lifetime_min`**: `"8"` - Minimum lifetime of each emitted particle in seconds.
*   **`lifetime_max`**: `"15"` - Maximum lifetime of each emitted particle in seconds.
*   **`count_min`**: `"1"` - Minimum number of particles emitted per emission cycle.
*   **`count_max`**: `"1"` - Maximum number of particles emitted per emission cycle.
*   **`render_on_grid`**: `"1"` - Particles will be rendered on the game grid.
*   **`fade_based_on_lifetime`**: `"1"` - Particles will fade out as their lifetime decreases.
*   **`airflow_force`**: `"0.251"` - Controls the force of airflow affecting the particles.
*   **`emission_interval_min_frames`**: `"1"` - Minimum frames between particle emissions.
*   **`emission_interval_max_frames`**: `"1"` - Maximum frames between particle emissions.
*   **`image_animation_file`**: `"data/particles/image_emitters/circle_128.png"` - The image file used for particle animation.
*   **`image_animation_speed`**: `"5"` - Speed of the image animation.
*   **`image_animation_loop`**: `"0"` - Whether the image animation should loop.
*   **`image_animation_raytrace_from_center`**: `"1"` - Controls how raytracing is applied to the animation.
*   **`set_magic_creation`**: `"1"` - Likely related to how the particles are created within the game's magic system.
*   **`is_emitting`**: `"1"` - Ensures the emitter is active.

## LifetimeComponent

This component defines the overall lifetime of the entity itself.

### Key Attributes:

*   **`lifetime`**: `"260"` - The entity will exist for 260 seconds.

## AudioComponent

This component is present but its configuration suggests it's a placeholder or not actively used for this specific particle effect.

### Key Attributes:

*   **`file`**: `"data/audio/Desktop/event_cues.bank"`
*   **`event_root`**: `"event_cues/heart_fullhp"`