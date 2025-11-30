---
title: Coward Shot End Script
category: scripts
---

---

# Coward Shot End Script

This script handles the behavior of a projectile or entity that is part of a "coward shot" effect. Its primary function is to move a targeted entity backward based on the projectile's velocity and then potentially clean up associated effects.

## Key Functionality

*   **Targeted Movement:** The script identifies a specific target entity and moves it in the opposite direction of the projectile's current velocity. This creates a "push-back" effect.
*   **Effect Cleanup (Commented Out):** The script includes commented-out code that, if enabled, would search for and destroy child entities of the target that have the "coward_effect" tag. This suggests a mechanism for removing visual or gameplay effects associated with the coward shot.

## Core Components and Logic

### Entity Initialization

*   `entity_id`: Retrieves the unique identifier for the current entity running the script.
*   `x, y`: Stores the current position of the entity.
*   `vx, vy`: Initializes variables to store the entity's velocity.

### Velocity Retrieval

*   The script accesses the `VelocityComponent` of the entity to read its `mVelocity` vector. This is crucial for determining the direction and magnitude of the push-back effect.

### Target Identification

*   The script looks for a `VariableStorageComponent` to find a variable named "target".
*   This "target" variable is expected to hold the `entity_id` of the entity that will be affected by the coward shot.

### Target Manipulation

*   If a valid `target` entity is found:
    *   The script calculates a new position for the target by subtracting a fraction of the projectile's velocity (`vx * 0.02`, `vy * 0.02`) from the projectile's current position.
    *   `EntitySetTransform` and `EntityApplyTransform` are used to update the target's position.

### Effect Cleanup (Commented)

*   The commented section demonstrates how to:
    *   Get all child entities of the `target`.
    *   Iterate through these children.
    *   Check if a child entity has the "coward_effect" tag.
    *   If the tag is present, `EntityKill` is called to destroy that child entity.

## Usage Notes

*   This script is likely attached to a projectile or an entity that triggers the "coward shot" effect.
*   The "target" variable must be correctly set on the entity running this script for it to function.
*   The effect cleanup logic is currently disabled and would require uncommenting to be active.