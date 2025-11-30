---
title: Boss Meat Hair Segment (Thin)
category: entities
---

# Boss Meat Hair Segment (Thin)

This entity defines a thin hair segment for the boss meat. It inherits its core functionality from `hair_piece.xml` and `hair_piece_thin.xml`, with specific physics properties applied.

## Key Components

### VerletPhysicsComponent
This component governs the physics simulation of the hair segment, allowing it to behave like a flexible chain.

*   **stiffness**: `1.25` - Controls how rigid the hair segment is. Higher values mean less bending.
*   **num_points**: `6` - The number of points used in the Verlet simulation, affecting the smoothness and complexity of its movement.
*   **resting_distance**: `2.0` - The preferred distance between simulation points when the hair is not under tension.

### Base Components
The entity reuses existing definitions for hair pieces.

*   `data/entities/animals/boss_meat/hair_piece.xml` (x3)
*   `data/entities/animals/boss_meat/hair_piece_thin.xml` (x2)

This indicates that the entity is composed of multiple instances of these base hair segments, with the `hair_piece_thin.xml` likely defining the visual and physical characteristics of the thinner strands.