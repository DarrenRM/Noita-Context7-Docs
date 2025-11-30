---
title: Controls Stick Particle Emitter
category: entities
---

# Controls Stick Particle Emitter

This entity defines a particle emitter that visually represents controls for movement, specifically the WASD keys. It's designed to emit particles that animate based on an image sequence.

## Key Components

### ParticleEmitterComponent

This component handles the emission of particles.

*   **`emitted_material_name`**: `spark` - The material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity.
*   **`lifetime_min` / `lifetime_max`**: `0.5` / `1` - The duration each particle exists in seconds.
*   **`count_min` / `count_max`**: `1` / `1` - Emits a single particle per emission event.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`emission_interval_min_frames` / `emission_interval_max_frames`**: `1` / `1` - Particles are emitted every frame, creating a continuous stream.
*   **`emit_cosmetic_particles`**: `1` - These are visual effects, not gameplay-affecting particles.
*   **`image_animation_file`**: `data/particles/image_emitters/controls_stick.png` - The sprite sheet used for particle animation.
*   **`image_animation_speed`**: `5` - Controls the playback speed of the image animation.
*   **`image_animation_loop`**: `1` - The animation will loop continuously.
*   **`is_emitting`**: `1` - The emitter is active.
*   **`render_back`**: `1` - Particles are rendered behind other elements.

### LifetimeComponent

This component determines how long the entity itself persists.

*   **`lifetime`**: `350` - The entity will exist for 350 frames.

## Entity Tags

*   **`controls_wasd`**: This tag likely associates this particle effect with the WASD input controls.