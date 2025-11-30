---
title: Dripping Radioactive Liquid Prop
category: entities
---

# Dripping Radioactive Liquid Prop

This entity represents a source of dripping radioactive liquid. It inherits its base functionality from `base_dripping_liquid.xml` and utilizes particle emitters to simulate the radioactive material falling.

## Key Components

### Base Entity

*   **`Base file="data/entities/base_dripping_liquid.xml"`**: This indicates that the entity inherits properties and behaviors from a pre-defined base entity for dripping liquids. This likely includes physics, collision, and general liquid-like interactions.

### Particle Emitters

This entity uses two `ParticleEmitterComponent` instances to generate radioactive liquid particles.

*   **`ParticleEmitterComponent`**:
    *   **`emitted_material_name="radioactive_liquid"`**: Specifies that the particles being emitted are of the `radioactive_liquid` material.
    *   **`emission_interval_min_frames="5"`**: The minimum delay in frames between particle emissions for the first emitter.
    *   **`emission_interval_max_frames="15"`**: The maximum delay in frames between particle emissions for the first emitter.
    *   **`emission_interval_min_frames="40"`**: The minimum delay in frames between particle emissions for the second emitter.
    *   **`emission_interval_max_frames="80"`**: The maximum delay in frames between particle emissions for the second emitter.

The two emitters likely create a more dynamic and varied dripping effect, with one emitting more frequently than the other.