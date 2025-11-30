---
title: Small Explosion Trail Spark Particle
category: entities/particles
---

# Small Explosion Trail Spark Particle

This entity defines a small, fast-moving spark particle used in explosions. It inherits its base behavior from `base_spark_trail.xml`.

## Key Attributes

### VelocityComponent
Controls the particle's movement and how it interacts with air.

| Attribute      | Description                                     |
|----------------|-------------------------------------------------|
| `air_friction` | The amount of friction applied by the air.      |

### SetStartVelocityComponent
Determines the initial speed of the spark particle.

| Attribute             | Description                                                              |
|-----------------------|--------------------------------------------------------------------------|
| `randomize_speed.min` | The minimum initial speed of the particle.                               |
| `randomize_speed.max` | The maximum initial speed of the particle.                               |

## Inheritance

This particle inherits its core functionality and visual properties from `data/entities/particles/particle_explosion/base_spark_trail.xml`. Modifications here primarily affect its initial velocity.