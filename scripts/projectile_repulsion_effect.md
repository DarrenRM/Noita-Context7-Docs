---
title: Projectile Repulsion Effect
category: scripts
---

# Projectile Repulsion Effect

This script creates a repulsion effect for projectiles within a certain radius. When projectiles enter the specified radius around the entity executing this script, they are pushed away from the entity.

## Key Functionality

*   **Detects Projectiles:** Identifies all entities tagged as "projectile" within a defined radius.
*   **Calculates Repulsion Force:** Determines the strength of the repulsion based on the projectile's distance from the center. Closer projectiles experience a stronger force.
*   **Applies Velocity Change:** Modifies the velocity of detected projectiles to push them away from the source.

## Core Components

### `distance_full`

*   **Type:** `number`
*   **Description:** Defines the maximum radius (in pixels) within which projectiles will be affected by the repulsion.

### `EntityGetInRadiusWithTag`

*   **Purpose:** This function is used to find all entities within a specified area that possess a particular tag.
*   **Usage:** `EntityGetInRadiusWithTag(x, y, radius, tag)`
    *   `x`, `y`: Coordinates of the center of the search area.
    *   `radius`: The radius of the search area.
    *   `tag`: The tag to filter entities by (e.g., "projectile").

### `EntityGetComponent` and `edit_component`

*   **Purpose:** These functions are used to access and modify components of an entity.
*   **Usage:**
    *   `EntityGetComponent(entity_id, component_name)`: Retrieves a specific component from an entity.
    *   `edit_component(entity_id, component_name, function(comp, vars))`: Allows for modifying a component's properties using a provided function.

### `VelocityComponent`

*   **Purpose:** This component governs the movement and velocity of an entity.
*   **Key Property:** `mVelocity` (Vector2) - Represents the current velocity of the entity.

### `gravity_percent`

*   **Purpose:** A calculated value representing the intensity of the repulsion based on distance. It ranges from 1.0 (at the center) down to a minimum of 0.01 at the edge of `distance_full`.
*   **Calculation:** `math.max((distance_full - distance) / distance_full, 0.01)`

### `gravity_coeff`

*   **Type:** `number`
*   **Description:** A constant multiplier that scales the repulsion force.

## Script Logic Breakdown

1.  **Get Entity Information:** Retrieves the ID and transform (position) of the entity executing the script.
2.  **Define Repulsion Radius:** Sets the `distance_full` variable to 96 pixels.
3.  **Find Projectiles:** Uses `EntityGetInRadiusWithTag` to find all entities tagged "projectile" within the `distance_full` radius.
4.  **Iterate Through Projectiles:** If projectiles are found, the script loops through each one.
5.  **Calculate Distance and Direction:** For each projectile, it calculates the distance from the source entity and the direction vector pointing away from the source.
6.  **Determine Repulsion Strength:** Calculates `gravity_percent` based on the projectile's distance.
7.  **Modify Velocity:**
    *   Retrieves the `VelocityComponent` of the projectile.
    *   If the component exists, it uses `edit_component` to modify the `mVelocity`.
    *   Calculates an `offset_x` and `offset_y` based on the direction and the calculated repulsion force (`gravity_coeff * gravity_percent`).
    *   Adds this offset to the projectile's current velocity, effectively pushing it away.