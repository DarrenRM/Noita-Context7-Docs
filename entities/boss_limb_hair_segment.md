---
title: Boss Limb Hair Segment
category: entities
---

# Boss Limb Hair Segment

This entity defines a segment of the boss's hair, utilizing physics to simulate its movement.

## Core Components

### InheritTransformComponent
This component is present but empty, indicating it inherits transform properties from its parent or base entities.

### VerletPhysicsComponent
This component governs the physics simulation of the hair segment.
*   **stiffness**: `1.25` - Controls how rigid the hair segment is.
*   **num_points**: `5` - The number of points used in the Verlet simulation, affecting the smoothness and complexity of the simulation.
*   **resting_distance**: `1.0` - The preferred distance between simulation points when the hair is at rest.

### Base Entities
This entity is composed of several base entities, defining its visual and functional aspects.
*   `data/entities/animals/boss_limbs/hair_piece.xml` (x3) - The primary components for the hair segments.
*   `data/entities/animals/boss_limbs/hair_piece_thin.xml` (x1) - A thinner variant of the hair piece, likely for visual variation.