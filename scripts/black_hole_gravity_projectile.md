---
title: Black Hole Gravity Projectile
category: scripts
---

---

# Black Hole Gravity Projectile

This script defines the behavior of a "black hole" projectile that exerts a gravitational pull on nearby entities.

## Core Functionality

The primary function of this script is to simulate a localized gravitational field. It achieves this by:

*   **Attracting Projectiles:** Pulling other projectiles towards its center.
*   **Applying Force to Physics Bodies:** Exerting a force on any physics bodies within its radius, proportional to their mass.

## Key Attributes and Mechanics

### Gravity Calculation

The `calculate_force_at` function determines the gravitational force applied to an entity based on its distance from the black hole.

*   **`distance_full`**: Defines the maximum radius (in pixels) at which the black hole's gravity is effective.
*   **`gravity_coeff`**: A constant multiplier that scales the gravitational force.
*   **`gravity_percent`**: A value between 0 and 1, representing how close an entity is to the black hole. Closer entities experience stronger gravity.

### Projectile Attraction

The script iterates through entities tagged as "projectile" within the `distance_full` radius.

*   **Targeting:** It specifically targets entities with a `VelocityComponent`.
*   **Force Application:** It calculates the necessary force using `calculate_force_at` and directly modifies the `mVelocity` of the targeted projectile's `VelocityComponent`.

### Physics Body Force Field

The script also applies a broader force field to physics bodies within a defined area.

*   **`PhysicsApplyForceOnArea`**: This function is used to apply a custom force calculation to all physics bodies within a rectangular area.
*   **`calculate_force_for_body`**: This function is called for each physics body. It calculates the force based on the entity's position, mass, and velocity, then scales it by `0.2 * body_mass`.

## Important Notes for Modding

*   **Entity Tagging:** Ensure that entities intended to be affected by the black hole have the appropriate tags (e.g., "projectile").
*   **Component Requirements:** Projectiles need a `VelocityComponent` to be affected. Physics bodies will be affected if they have a `PhysicsBody2Component` or `PhysicsBodyComponent`.
*   **Force Scaling:** The `gravity_coeff` and the `0.2 * body_mass` multiplier in `calculate_force_for_body` are key parameters to adjust for tuning the black hole's strength.
*   **Radius Control:** `distance_full` directly controls the range of the black hole's influence.