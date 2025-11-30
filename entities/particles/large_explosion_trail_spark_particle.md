---
title: Large Explosion Trail Spark Particle
category: entities/particles
---

# Large Explosion Trail Spark Particle

This document describes the configuration for a large spark particle used in explosions within Noita, intended for AI-assisted modding.

## Entity Configuration

The particle inherits its base properties from `base_spark_trail.xml`.

### Key Components and Attributes

*   **`VelocityComponent`**:
    *   `air_friction`: Controls how quickly the particle loses velocity in the air. A value of `8.0` indicates significant air resistance.

*   **`DieIfSpeedBelowComponent`**:
    *   `min_speed`: The minimum speed the particle must maintain to avoid being destroyed. Set to `30`, meaning particles slower than this will disappear.

*   **`ParticleEmitterComponent`**: This entity utilizes multiple `ParticleEmitterComponent` instances to define the behavior and lifespan of the emitted sparks.

    *   **Emitter 1 (Implicitly from base)**: Inherits default emitter properties.
    *   **Emitter 2**:
        *   `lifetime_max`: `2.4` seconds. This emitter contributes sparks with a maximum lifespan of 2.4 seconds.
    *   **Emitter 3**:
        *   `lifetime_max`: `0.6` seconds. This emitter contributes sparks with a maximum lifespan of 0.6 seconds, creating a shorter-lived trail.

This configuration allows for a dynamic visual effect where sparks of varying lifespans are generated, contributing to the overall explosion trail.