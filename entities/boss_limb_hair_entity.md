---
title: Boss Limb Hair Entity
category: entities
---

---

# Boss Limb Hair Entity

This entity defines a component of a boss's limb, specifically its "hair." It inherits functionality from `hair_piece.xml` and `hair_piece_thin.xml` to create a segmented, physics-driven visual element.

## Key Components

### InheritTransformComponent
*   **Purpose:** Inherits transformation properties from its parent entity. This is a standard component for entities that are part of a larger structure.

### VerletPhysicsComponent
*   **Purpose:** Implements Verlet physics for dynamic, flexible movement.
*   **Key Attributes:**
    *   `stiffness`: Controls how rigid the "hair" segments are. A value of `1.25` suggests moderate flexibility.
    *   `num_points`: Defines the number of points used in the Verlet simulation, influencing the smoothness and complexity of the hair's movement.
    *   `resting_distance`: The preferred distance between points when the physics simulation is at rest.

### Base Components
*   **Purpose:** This entity is composed of multiple instances of other "hair piece" entities, creating a segmented appearance.
*   **Inherited Files:**
    *   `data/entities/animals/boss_limbs/hair_piece.xml` (3 instances)
    *   `data/entities/animals/boss_limbs/hair_piece_thin.xml` (2 instances)

This composition allows for a more complex and visually interesting "hair" effect by combining different types of hair segments.