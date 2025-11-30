---
title: Explosion Trail Spark Short
category: entities/particles
---

# Explosion Trail Spark Short

This entity defines a short-lived spark particle used in explosions. It inherits its base behavior from `base_spark_trail.xml`.

## Key Attributes

### VelocityComponent
Controls the particle's movement and how it interacts with air.

| Attribute     | Description                               |
|---------------|-------------------------------------------|
| `air_friction`| The amount of friction applied by air.    |

### SetStartVelocityComponent
Determines the initial speed of the spark particle.

| Attribute           | Description                                     |
|---------------------|-------------------------------------------------|
| `randomize_speed.min`| The minimum initial speed.                      |
| `randomize_speed.max`| The maximum initial speed.                      |

### DieIfSpeedBelowComponent
Specifies the speed at which the particle will disappear.

| Attribute    | Description                               |
|--------------|-------------------------------------------|
| `min_speed`  | The minimum speed before the particle dies.|