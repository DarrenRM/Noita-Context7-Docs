---
title: Spitter Particle Effect
category: entities
---

# Spitter Particle Effect

This document describes the XML configuration for the "Spitter" particle effect in Noita, designed for AI-assisted modding.

## Entity Configuration

The `Spitter.xml` file defines a simple entity primarily focused on particle emission.

### Key Components

*   **`LifetimeComponent`**:
    *   `lifetime`: The total duration this particle effect will exist.
        *   `lifetime="3"`: The effect lasts for 3 seconds.

*   **`ParticleEmitterComponent`**: This component governs the creation and behavior of the particles.
    *   `emitted_material_name`: Specifies the material of the particles to be emitted.
        *   `emitted_material_name="plasma_fading_pink"`: The particles will be of the "plasma\_fading\_pink" material.
    *   `lifetime_min`, `lifetime_max`: The minimum and maximum lifespan of individual particles.
        *   `lifetime_min="0.05"`
        *   `lifetime_max="0.2"`
    *   `x_pos_offset_min`, `x_pos_offset_max`, `y_pos_offset_min`, `y_pos_offset_max`: Define the random offset from the emitter's position where particles can spawn.
        *   `x_pos_offset_min="-2"`
        *   `x_pos_offset_max="2"`
        *   `y_pos_offset_min="-2"`
        *   `y_pos_offset_max="2"`
    *   `x_vel_min`, `x_vel_max`, `y_vel_min`, `y_vel_max`: Define the initial velocity range for emitted particles.
        *   `x_vel_min="-80"`
        *   `x_vel_max="0"`
        *   `y_vel_min="-80"`
        *   `y_vel_max="80"`
    *   `gravity.y`: The gravitational pull affecting the particles.
        *   `gravity.y="0.0"`: Particles are not affected by gravity in the Y-axis.
    *   `count_min`, `count_max`: The minimum and maximum number of particles emitted per emission cycle.
        *   `count_min="7"`
        *   `count_max="15"`
    *   `render_on_grid`: Whether the particles should be rendered on the game grid.
        *   `render_on_grid="1"`: Particles are rendered.
    *   `fade_based_on_lifetime`: If particles should fade out as their lifetime decreases.
        *   `fade_based_on_lifetime="1"`: Particles will fade.
    *   `cosmetic_force_create`: Forces the creation of cosmetic particles.
        *   `cosmetic_force_create="0"`: Not forced cosmetic.
    *   `emission_interval_min_frames`, `emission_interval_max_frames`: The minimum and maximum frames between particle emissions.
        *   `emission_interval_min_frames="1"`
        *   `emission_interval_max_frames="1"`: Particles are emitted every frame.
    *   `emit_cosmetic_particles`: Whether to emit cosmetic particles.
        *   `emit_cosmetic_particles="1"`: Cosmetic particles are emitted.
    *   `is_emitting`: Controls if the emitter is currently active.
        *   `is_emitting="1"`: The emitter is active.