---
title: Teal Slime Tentacle 03 Entity
category: entities
---

# Teal Slime Tentacle 03 Entity

This entity defines a segment of a teal slime tentacle, utilizing Verlet physics for its chain-like behavior. It inherits its core properties from a base tentacle piece and then adds specific physics configurations.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the tentacle segment, making it behave like a flexible chain.

*   **`stiffness`**: `1.25` - Controls how rigid the tentacle chain is. Higher values mean less bending.
*   **`num_points`**: `8` - The number of points used to simulate the chain. More points allow for more detailed bending.
*   **`velocity_dampening`**: `0.8` - Reduces the velocity of the points over time, helping the tentacle settle.
*   **`resting_distance`**: `2.0` - The preferred distance between adjacent points in the chain when it's not under stress.

### Base Components

The entity inherits its visual and functional aspects from multiple base files, creating the segmented tentacle structure.

*   **`data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml`**: This base file is inherited multiple times, forming the main body of the tentacle.
*   **`data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml`**: This base file is inherited twice, likely to create thinner segments towards the end of the tentacle.

```xml
<Entity>

	<InheritTransformComponent>
	</InheritTransformComponent>

    <VerletPhysicsComponent
    	stiffness="1.25"
    	num_points="8"
		velocity_dampening="0.8"
    	resting_distance="2.0" >
    </VerletPhysicsComponent>

	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml" />
	<Base file="data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml" />

</Entity>
```