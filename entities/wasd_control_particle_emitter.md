---
title: WASD Control Particle Emitter
category: entities
---

# WASD Control Particle Emitter

This entity defines a particle emitter that visually represents WASD key presses, likely for UI or tutorial purposes.

## Entity Definition

The core of this entity is a `ParticleEmitterComponent` that generates cosmetic particles.

### Key Components

*   **`ParticleEmitterComponent`**:
    *   `emitted_material_name`: Specifies the material of the particles to be emitted. Here, it's set to `"spark"`.
    *   `lifetime_min`, `lifetime_max`: Controls the duration each emitted particle exists, ranging from 0.5 to 1 second.
    *   `count_min`, `count_max`: Determines the number of particles emitted per emission event, fixed at 1.
    *   `render_on_grid`: Set to `1`, meaning particles are rendered even when the game grid is not visible.
    *   `fade_based_on_lifetime`: Set to `1`, particles will fade out as their lifetime decreases.
    *   `area_circle_radius.min`, `area_circle_radius.max`: Set to `0`, indicating particles are emitted from a single point.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: Set to `1`, meaning particles are emitted continuously with no delay between frames.
    *   `emit_cosmetic_particles`: Set to `1`, indicating these are purely visual effects.
    *   `image_animation_file`: Points to the sprite sheet used for particle animation: `"data/particles/image_emitters/controls_wasd.png"`.
    *   `image_animation_speed`: Controls the playback speed of the image animation, set to `5`.
    *   `image_animation_loop`: Set to `1`, the animation will loop continuously.
    *   `is_emitting`: Set to `1`, the emitter is active.
    *   `render_back`: Set to `1`, particles are rendered behind other elements.

*   **`LifetimeComponent`**:
    *   `lifetime`: Sets the overall duration for which this entity (and thus the emitter) exists, at `350` frames.

## Usage Notes

This entity is likely triggered by player input to display visual cues for WASD movement. The `_enabled="0"` attribute on both components suggests it's designed to be activated dynamically by game logic rather than being active from the start.