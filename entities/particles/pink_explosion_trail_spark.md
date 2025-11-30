---
title: Pink Explosion Trail Spark
category: entities/particles
---

```

# Pink Explosion Trail Spark

This entity defines a specific type of particle trail used in explosions, characterized by its pink color. It inherits its base functionality from `base_spark_trail.xml` and customizes the emitted material.

## Key Components

### Base Entity

*   **`Base file="data/entities/particles/particle_explosion/base_spark_trail.xml"`**: This indicates that the entity inherits all properties and behaviors from the `base_spark_trail.xml` file. This is the foundation for the spark trail's visual and functional aspects.

### Particle Emitter Components

This entity utilizes two `ParticleEmitterComponent` instances to define the particles that make up the trail.

*   **`emitted_material_name="plasma_fading_pink"`**: This is the crucial attribute that defines the visual appearance of the emitted particles. It specifies that the particles should be of the "plasma_fading_pink" material, which dictates their color, fading behavior, and other visual properties.

---