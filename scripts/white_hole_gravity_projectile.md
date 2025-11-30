---
title: White Hole Gravity Projectile
category: scripts
---

---

# White Hole Gravity Projectile

This script defines the behavior of a "white hole" projectile that exerts a gravitational pull on nearby projectiles and applies a force field to physics bodies.

## Key Attributes

*   **`distance_full`**: The maximum radius (in pixels) at which the gravity effect is applied.
*   **`gravity_coeff`**: A multiplier that determines the strength of the gravitational pull.

## Core Functionality

### `calculate_force_at(body_x, body_y)`

This function calculates the gravitational force to be applied to an entity at a given position (`body_x`, `body_y`) relative to the white hole's position (`x`, `y`).

*   **Distance Calculation**: Determines the distance between the white hole and the target entity.
*   **Direction Calculation**: Calculates the direction vector from the target entity towards the white hole.
*   **Gravity Percentage**: A value between 0 and 1, representing how close the target entity is to the white hole within the `distance_full` radius. Closer entities experience stronger gravity.
*   **Force Calculation**: Computes the X and Y components of the gravitational force, inversely proportional to the distance and directly proportional to `gravity_coeff` and `gravity_percent`.

### Projectile Attraction

The script iterates through all entities tagged as "projectile" within the `distance_full` radius.

*   **Physics Component Check**: It checks if the projectile has a `PhysicsBody2Component` or `PhysicsBodyComponent` and is not tagged as "black_hole".
*   **Velocity Update**: If a `VelocityComponent` is found, the calculated gravitational force is added to the projectile's existing velocity, pulling it towards the white hole.

### Physics Body Force Field

The script applies a force field to all physics bodies within a specified area around the white hole.

*   **`calculate_force_for_body(...)`**: This function is called for each physics body within the force field area.
    *   It calculates the base gravitational force using `calculate_force_at`.
    *   The force is then scaled by `0.2` and the `body_mass` of the physics body.
    *   It returns the position, calculated force (X and Y), and zero angular force.
*   **`PhysicsApplyForceOnArea(...)`**: This Noita API function applies the calculated forces to physics bodies within the defined area. The area is a square centered on the white hole with a side length of `distance_full`.