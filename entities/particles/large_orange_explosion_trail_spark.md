---
title: Large Orange Explosion Trail Spark
category: entities/particles
---

# Large Orange Explosion Trail Spark

This entity defines a large orange spark particle used in explosions. It inherits its base properties from `base_spark_trail.xml` and customizes its behavior and emission.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_spark_trail.xml"`**: Inherits core particle explosion trail functionality.

### Velocity Component

*   **`air_friction="8.0"`**: Specifies the air friction applied to the particle, influencing its deceleration.

### Die If Speed Below Component

*   **`min_speed="30"`**: The particle will be destroyed if its speed drops below this threshold.

### Particle Emitter Components

This entity utilizes multiple `ParticleEmitterComponent` instances to control the emission of "spark" materials with varying lifetimes.

*   **Emitter 1:**
    *   **`emitted_material_name="spark"`**: The material emitted by this component.
*   **Emitter 2:**
    *   **`emitted_material_name="spark"`**: The material emitted.
    *   **`lifetime_max="2.4"`**: The maximum lifetime of particles emitted by this component is 2.4 seconds.
*   **Emitter 3:**
    *   **`emitted_material_name="spark"`**: The material emitted.
    *   **`lifetime_max="0.6"`**: The maximum lifetime of particles emitted by this component is 0.6 seconds.