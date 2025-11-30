---
title: Shaman Lantern Entity Script
category: scripts
---

# Shaman Lantern Entity Script

This script defines the behavior for the Shaman Lantern entity in Noita. It primarily controls its rotational movement based on its velocity and a momentum factor.

## Key Attributes

### Movement Logic

*   **`momentum`**: Controls how much the entity's previous velocity influences its current swing. A value of `0.9` suggests a significant carry-over.
*   **`range`**: Determines the maximum angle the lantern can swing.
*   **`swing`**: A dynamic variable that accumulates velocity influence and momentum.
    *   It's calculated by taking the absolute sum of X and Y velocities, scaled by 100.
    *   This accumulated value is then multiplied by `momentum`.
    *   The result is clamped between -1000 and 1000 to prevent extreme values.
*   **Angular Calculation**: The final angle is determined by a sine wave function.
    *   The input to the sine function is `GameGetFrameNum() * 0.15 - swing`. This means the oscillation speed is influenced by the game frame rate, and the phase is shifted by the calculated `swing` value.
    *   The result of the sine wave is multiplied by `range` and the scaled `swing` value (`swing * 0.001`), creating an oscillating angle that is amplified by the entity's movement.

### Entity Interaction

*   **`entity_id`**: Retrieves the unique identifier for the current entity.
*   **`EntityGetTransform`**: Gets the current position (`x`, `y`) and `angle` of the entity.
*   **`GameGetVelocityCompVelocity`**: Retrieves the velocity components (`vx`, `vy`) of the entity's root.
*   **`get_variable_storage_component`**: Accesses a storage component named "swing" to manage the `swing` variable across frames.
*   **`component_readwrite`**: Allows reading and writing to the storage component, updating the `swing` variable.
*   **`clamp`**: A utility function to keep the `swing` value within a specified range.
*   **`EntitySetTransform`**: Updates the entity's transform, applying the calculated `angle` while preserving its position.