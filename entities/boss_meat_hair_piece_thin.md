---
title: Boss Meat Hair Piece (Thin)
category: entities
---

# Boss Meat Hair Piece (Thin)

This entity defines a thin hair piece component for the boss meat. It inherits its core functionality from `hair_piece_thin.xml` and utilizes Verlet physics to simulate its movement.

## Key Components

### VerletPhysicsComponent

This component governs the physics simulation of the hair piece.

| Attribute        | Value   | Description                                     |
| :--------------- | :------ | :---------------------------------------------- |
| `stiffness`      | `1.25`  | Controls the rigidity of the hair piece.        |
| `num_points`     | `7`     | The number of points used in the Verlet simulation. |
| `resting_distance` | `1.0`   | The preferred distance between simulation points. |

### Base Component

This entity is composed of multiple instances of `hair_piece_thin.xml`, suggesting it's a collection of these thin hair pieces.

```xml
<Entity>
	<InheritTransformComponent>
	</InheritTransformComponent>

    <VerletPhysicsComponent
    	stiffness="1.25"
    	num_points="7"
    	resting_distance="1.0" >
    </VerletPhysicsComponent>

	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
	<Base file="data/entities/animals/boss_meat/hair_piece_thin.xml" />
</Entity>
```