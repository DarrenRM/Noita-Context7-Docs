---
title: Large Purple Explosion Spark Trail Particle
category: entities
---

# Large Purple Explosion Spark Trail Particle

This entity defines a large, purple spark trail particle used in explosions. It inherits its base behavior from `base_spark_trail.xml` and customizes its emission properties.

## Key Attributes

### Base Entity

*   **file**: `data/entities/particles/particle_explosion/base_spark_trail.xml` - Inherits core particle trail functionality.

### VelocityComponent

*   **air_friction**: `8.0` - Controls how quickly the particle loses speed due to air resistance.

### DieIfSpeedBelowComponent

*   **min_speed**: `30` - The particle will be destroyed if its speed drops below this threshold.

### ParticleEmitterComponent (Multiple Instances)

This entity utilizes multiple `ParticleEmitterComponent` instances to control different aspects of the spark trail's appearance and lifetime.

*   **Instance 1 (Default Lifetime):**
    *   **emitted_material_name**: `spark_purple_bright` - Specifies the material of the emitted sparks.

*   **Instance 2 (Longer Lifetime):**
    *   **emitted_material_name**: `spark_purple_bright` - Specifies the material of the emitted sparks.
    *   **lifetime_max**: `2.4` - The maximum lifetime of particles emitted by this component.

*   **Instance 3 (Shorter Lifetime):**
    *   **emitted_material_name**: `spark_purple_bright` - Specifies the material of the emitted sparks.
    *   **lifetime_max**: `0.6` - The maximum lifetime of particles emitted by this component.

This configuration allows for a trail of purple sparks with varying lifespans, creating a dynamic visual effect.