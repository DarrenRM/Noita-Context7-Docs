---
title: Teleport Projectile Closer Initialization
category: scripts
---

---

# Teleport Projectile Closer Initialization

This script initializes the `teleport_projectile_closer` component for a projectile. It records the projectile's initial position to be used later for teleportation logic.

## Key Components and Attributes

### VariableStorageComponent

This component is used to store variables associated with the entity.

*   **`name`**: The name of the variable being stored.
    *   `origin_x`: Stores the X-coordinate of the projectile's origin.
    *   `origin_y`: Stores the Y-coordinate of the projectile's origin.
*   **`value_float`**: The float value to be stored for the variable.

## Script Logic

1.  **Get Entity ID and Position**: Retrieves the unique identifier and current world coordinates (`pos_x`, `pos_y`) of the projectile entity.
2.  **Access Variable Storage**: Searches for a `VariableStorageComponent` with the specific identifier `"teleport_closer"`.
3.  **Update Origin Coordinates**: If the component is found, it iterates through its stored variables.
    *   If a variable named `"origin_x"` is found, its `value_float` is updated to the projectile's current `pos_x`.
    *   If a variable named `"origin_y"` is found, its `value_float` is updated to the projectile's current `pos_y`.

This ensures that the projectile "remembers" where it started, which is crucial for its subsequent teleportation behavior.