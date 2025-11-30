---
title: Boss Meat Hair Segment
category: entities
---

# Boss Meat Hair Segment

This entity defines a segment of the "boss meat" hair, likely used for visual effects or physics interactions on a boss entity. It inherits its core functionality from `hair_piece.xml` and `hair_piece_thin.xml`, suggesting it's a modular component.

## Key Components

### InheritTransformComponent
This component indicates that the entity inherits transformation properties (position, rotation, scale) from its parent or a base entity.

### VerletPhysicsComponent
This component enables Verlet physics simulation for the hair segment.

*   **stiffness**: `1.25` - Controls the elasticity and resistance to deformation.
*   **num_points**: `5` - Defines the number of points used in the Verlet simulation, influencing the complexity and smoothness of the physics.
*   **resting_distance**: `1.0` - The preferred distance between simulation points when no forces are applied.

### Base Components
This entity utilizes multiple `Base` components to inherit properties and functionality from other entities.

*   `data/entities/animals/boss_meat/hair_piece.xml` (included 3 times)
*   `data/entities/animals/boss_meat/hair_piece_thin.xml` (included 1 time)

This suggests that the "boss meat" hair is composed of several interconnected segments, with variations in thickness or appearance.