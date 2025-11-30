---
title: Large Green Explosion Trail Spark
category: entities/particles
---

# Large Green Explosion Trail Spark

This entity defines a large green spark particle used in explosions. It inherits its base properties from `base_spark_trail.xml` and customizes its emission and behavior.

## Key Components

### Base Entity

*   **Inheritance:** `data/entities/particles/particle_explosion/base_spark_trail.xml` - This indicates it uses a pre-defined template for spark trails.

### VelocityComponent

*   **`air_friction`**: `8.0` - Controls how quickly the particle loses velocity due to air resistance. A higher value means faster deceleration.

### DieIfSpeedBelowComponent

*   **`min_speed`**: `30` - The particle will be destroyed if its speed drops below this threshold. This helps particles fade out naturally.

### ParticleEmitterComponent (Multiple Instances)

This entity utilizes multiple `ParticleEmitterComponent` instances to control the emission of the `spark_green` material with varying lifetimes.

*   **Instance 1:**
    *   **`emitted_material_name`**: `spark_green` - Specifies the material of the emitted particles.
*   **Instance 2:**
    *   **`emitted_material_name`**: `spark_green`
    *   **`lifetime_max`**: `2.4` - The maximum lifetime of particles emitted by this component is 2.4 seconds.
*   **Instance 3:**
    *   **`emitted_material_name`**: `spark_green`
    *   **`lifetime_max`**: `0.6` - The maximum lifetime of particles emitted by this component is 0.6 seconds.

This setup allows for a more dynamic visual effect by having sparks with different durations.