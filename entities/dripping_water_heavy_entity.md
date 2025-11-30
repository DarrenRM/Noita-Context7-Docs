---
title: Dripping Water (Heavy) Entity
category: entities
---

# Dripping Water (Heavy) Entity

This document describes the `dripping_water_heavy.xml` entity, which represents a source of heavy dripping water in Noita.

## Key Attributes

The `dripping_water_heavy.xml` entity inherits its core functionality from `base_dripping_liquid.xml`. The primary customization for this specific entity is its particle emission behavior.

### Entity Definition

*   **`tags`**: `mortal`, `hittable`
    *   `mortal`: Indicates the entity can be destroyed.
    *   `hittable`: Indicates the entity can be affected by damage.

### Base Entity

*   **`Base file="data/entities/base_dripping_liquid.xml"`**: This specifies that the entity inherits properties and behaviors from the generic `base_dripping_liquid.xml` file. This likely includes its liquid properties, dripping mechanics, and interaction with the environment.

### Particle Emitter Component

*   **`ParticleEmitterComponent`**: This component controls the generation of particles that visually represent the dripping water.
    *   **`emission_interval_min_frames`**: `5` - The minimum number of frames between particle emissions.
    *   **`emission_interval_max_frames`**: `15` - The maximum number of frames between particle emissions.

This configuration suggests a relatively frequent but not constant emission of water particles, contributing to the visual effect of heavy dripping.