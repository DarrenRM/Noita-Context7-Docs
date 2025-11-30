---
title: Red Crystal Effect
category: entities
---

---

# Red Crystal Effect

This entity defines the visual and physical effects associated with a red crystal. It primarily focuses on particle emission and the behavior of loose ground when the crystal is present.

## Key Components

### ParticleEmitterComponent

This component controls the visual particles emitted by the red crystal.

*   **`emitted_material_name`**: `spark_red` - Specifies the material of the particles being emitted.
*   **`gravity.y`**: `0.0` - Particles have no vertical gravity, meaning they float.
*   **`lifetime_min` / `lifetime_max`**: `3` / `8` - The duration each particle exists in seconds.
*   **`count_min` / `count_max`**: `4` / `4` - The number of particles emitted per emission cycle.
*   **`render_on_grid`**: `1` - Particles are rendered even on the game grid.
*   **`fade_based_on_lifetime`**: `1` - Particles fade out as their lifetime decreases.
*   **`airflow_force`**: `0.251` - The force applied to particles by airflow.
*   **`image_animation_file`**: `data/particles/image_emitters/animated_emitter.png` - The sprite sheet used for particle animation.
*   **`image_animation_speed`**: `4` - The speed of the particle animation.

### LooseGroundComponent

This component governs the behavior of loose ground when the red crystal is active.

*   **`probability`**: `0.4` - The chance that loose ground will be generated.
*   **`max_distance`**: `100` - The maximum distance from the crystal at which loose ground can form.
*   **`min_radius` / `max_radius`**: `6` / `16` - The range of radii for the generated loose ground.
*   **`collapse_images`**: `data/procedural_gfx/collapse_big/$[0-14].png` - The image sequence used for the collapse animation of loose ground.

### LifetimeComponent

This component determines how long the red crystal entity itself persists.

*   **`lifetime`**: `280` - The base duration the entity exists in seconds.
*   **`randomize_lifetime.min` / `randomize_lifetime.max`**: `-50` / `50` - Adds a random variation to the entity's lifetime.