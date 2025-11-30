---
title: Large Red Explosion Spark Trail Particle
category: entities/particles
---

# Large Red Explosion Spark Trail Particle

This entity defines a large, red spark particle used in explosions. It inherits its base behavior from `base_spark_trail.xml` and customizes its emission and lifespan.

## Key Attributes

### Base Entity

*   **file**: `data/entities/particles/particle_explosion/base_spark_trail.xml`
    *   Indicates that this particle inherits properties from a common spark trail base.

### Velocity Component

*   **air_friction**: `8.0`
    *   Controls how quickly the particle loses velocity due to air resistance. A higher value means faster deceleration.

### Die If Speed Below Component

*   **min_speed**: `30`
    *   The particle will be destroyed if its speed drops below this threshold. This helps particles fade out naturally.

### Particle Emitter Components

This entity utilizes multiple `ParticleEmitterComponent` instances to control the emission of `spark_red` material with varying lifespans.

*   **First Emitter:**
    *   **emitted_material_name**: `spark_red`
        *   Specifies the material of the emitted particles.
*   **Second Emitter:**
    *   **emitted_material_name**: `spark_red`
    *   **lifetime_max**: `2.4`
        *   The maximum lifespan of particles emitted by this component is 2.4 seconds.
*   **Third Emitter:**
    *   **emitted_material_name**: `spark_red`
    *   **lifetime_max**: `0.6`
        *   The maximum lifespan of particles emitted by this component is 0.6 seconds.

This setup allows for a more dynamic visual effect, with sparks of different durations contributing to the overall explosion trail.