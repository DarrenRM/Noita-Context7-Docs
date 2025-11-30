---
title: Clipping Shot Projectile Modification
category: scripts
---

---

# Clipping Shot Projectile Modification

This script modifies the behavior of a projectile, specifically enhancing its ability to penetrate the environment and adjust its friction. It targets the projectile's `ProjectileComponent` and `VelocityComponent` to achieve these effects.

## Key Modifications

### ProjectileComponent Adjustments

This section focuses on altering the projectile's penetration and friction properties.

*   **`penetrate_world`**: Set to `1`, enabling the projectile to pass through world geometry.
*   **`penetrate_world_velocity_coeff`**: Set to `0.1`. This coefficient likely influences how much velocity is retained or lost when penetrating the world. A lower value might mean less velocity loss.
*   **`friction`**: The projectile's existing friction value is read, clamped to a minimum of `0`, and then reapplied. This ensures friction doesn't become negative.

### VelocityComponent Adjustments

This section modifies the projectile's air friction.

*   **`air_friction`**: The projectile's existing air friction value is read, clamped to a minimum of `0`, and then reapplied. This ensures air friction doesn't become negative.

## Script Logic

1.  **Initialization**:
    *   Retrieves the current entity ID and its transform (position).
    *   Identifies the parent entity ID.
    *   Determines the `target_id`: if the projectile has a parent, it's the parent; otherwise, it's the projectile itself.

2.  **Component Retrieval**:
    *   Attempts to retrieve `ProjectileComponent` and `VelocityComponent` from the `target_id`.
    *   If `ProjectileComponent` is not found, the script exits.

3.  **ProjectileComponent Modification**:
    *   If `ProjectileComponent` exists, it iterates through its components (though typically there's only one relevant for a projectile).
    *   Uses `edit_component` to modify `penetrate_world`, `penetrate_world_velocity_coeff`, and `friction`.

4.  **VelocityComponent Modification**:
    *   If `VelocityComponent` exists, it iterates through its components.
    *   Uses `edit_component` to modify `air_friction`.

## Usage Notes for Modders

*   This script is designed to be attached to a projectile entity.
*   The `target_id` logic ensures that modifications are applied to the entity that is actually firing the projectile, or the projectile itself if it's not parented.
*   The clamping of friction values (`math.max(0, ...)`) is a safety measure to prevent unexpected behavior from negative friction.
*   Understanding the interplay between `penetrate_world` and `penetrate_world_velocity_coeff` is crucial for fine-tuning projectile behavior.