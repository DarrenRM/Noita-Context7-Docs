---
title: Small Tentacle Physics (Tentacle 02)
category: entities
---

# Small Tentacle Physics (Tentacle 02)

This document details the physics properties of a specific small tentacle entity in Noita, focusing on its Verlet physics simulation.

## Entity Structure

The entity primarily inherits its base properties from other tentacle XML files, with specific physics configurations applied.

```xml
<Entity>
    <InheritTransformComponent/>
    <VerletPhysicsComponent
        stiffness="1.25"
        num_points="7"
        velocity_dampening="0.8"
        resting_distance="1.0"
        pixelate_sprite_transforms="0"
        animation_target_offset.y="1.0"
        animation_energy="0.16"
        stain_cells_probability="10"
    >
    </VerletPhysicsComponent>

    <!-- Inherited base files -->
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml" />
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml" />
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_3.xml" />
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />
    <Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />
</Entity>
```

## VerletPhysicsComponent Key Attributes

This component defines how the tentacle behaves as a chain of connected points, simulating a flexible, physics-driven object.

| Attribute             | Value   | Description                                                                                                |
| :-------------------- | :------ | :--------------------------------------------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the tentacle chain is. Higher values mean less bending.                                 |
| `num_points`          | `7`     | The number of points (segments) that make up the tentacle chain. More points allow for more detailed bending. |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of the tentacle points over time, causing it to settle and lose momentum.             |
| `resting_distance`    | `1.0`   | The ideal distance between connected points when the tentacle is not under stress.                         |
| `animation_target_offset.y` | `1.0` | An offset applied to the animation target in the Y-axis, influencing how the tentacle animates.            |
| `animation_energy`    | `0.16`  | Affects the intensity or strength of the tentacle's animation.                                             |
| `stain_cells_probability` | `10`    | The probability (out of 100) that the tentacle will leave stains on cells it interacts with.              |