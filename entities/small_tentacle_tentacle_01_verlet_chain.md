---
title: Small Tentacle (Tentacle 01) Verlet Chain
category: entities
---

# Small Tentacle (Tentacle 01) Verlet Chain

This entity defines a specific configuration for a small tentacle using the Verlet physics system. It inherits its core behavior from other `smalltentacle` XML files and applies specific physics properties to create its movement and appearance.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation for the tentacle.

| Attribute             | Value   | Description                                                                 |
| :-------------------- | :------ | :-------------------------------------------------------------------------- |
| `stiffness`           | `1.25`  | Controls how rigid the tentacle segments are. Higher values mean less bend. |
| `num_points`          | `9`     | The number of points (nodes) that make up the Verlet chain.                 |
| `velocity_dampening`  | `0.8`   | Reduces the velocity of the points over time, causing it to settle.         |
| `resting_distance`    | `1.0`   | The preferred distance between adjacent points when not under tension.      |
| `animation_target_offset.y` | `1.0` | An offset applied to the animation target in the Y-axis.                  |
| `animation_energy`    | `0.16`  | Influences the intensity or speed of animations applied to the chain.       |
| `stain_cells_probability` | `10`  | The probability (out of 100) that this entity will leave stains.            |

### Base Components

This entity utilizes multiple `<Base>` tags to inherit and combine properties from other tentacle configurations. This allows for modularity and reuse of tentacle designs.

*   `data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml` (3 times)
*   `data/entities/verlet_chains/smalltentacle/smalltentacle_3.xml` (2 times)
*   `data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml` (3 times)

These inherited files likely define the visual sprites, collision shapes, and potentially other behavioral aspects of the tentacle segments. The repetition suggests a layered or additive approach to defining the final tentacle's properties.

```xml
<Entity>

	<InheritTransformComponent>
	</InheritTransformComponent>

    <VerletPhysicsComponent
    	stiffness="1.25"
    	num_points="9"
		velocity_dampening="0.8"
    	resting_distance="1.0"
		pixelate_sprite_transforms="0"
		animation_target_offset.y="1.0"
		animation_energy="0.16"
		stain_cells_probability="10"
		>
    </VerletPhysicsComponent>

	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_2.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_3.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_3.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />
	<Base file="data/entities/verlet_chains/smalltentacle/smalltentacle_4.xml" />

</Entity>
```