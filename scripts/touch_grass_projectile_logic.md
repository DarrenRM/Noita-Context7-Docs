---
title: Touch Grass Projectile Logic
category: scripts
---

# Touch Grass Projectile Logic

This script controls the behavior of a projectile that interacts with the "touching grass" game mechanic. It primarily affects whether a projectile's particle emitter is active and influences a global variable based on the player's proximity to the sky.

## Core Functionality

### `init(entity_id)`

This function is called when the projectile entity is initialized.

*   **Purpose:** To disable the `MagicConvertMaterialComponent` if the projectile is currently "touching grass."
*   **Logic:**
    *   Checks the global variable `TOUCHING_GRASS`. If it's "1", it means the player is considered to be touching grass.
    *   If `TOUCHING_GRASS` is "1", it attempts to find and disable the `MagicConvertMaterialComponent` on the projectile entity. This component is likely responsible for material conversion, and disabling it prevents this effect when the projectile is in a "safe" state.

### Main Logic (Called by Custom Card Entity)

This section contains the primary logic executed by the projectile entity.

*   **Purpose:** To dynamically control the projectile's particle emission based on sky visibility and to update the global `TOUCHING_GRASS` variable when the projectile is held by the player.
*   **Key Variables:**
    *   `safe_sky_min`: A threshold value (0.2) for sky visibility.
*   **Logic:**
    1.  **Get Entity ID and Transform:** Retrieves the current entity's ID and its position (`x`, `y`).
    2.  **Calculate Sky Visibility:**
        *   Initializes `sky` to 0.
        *   Uses `GameGetSkyVisibility` to check the sky visibility at the projectile's current position and adjacent points (up, left, right). This is a simplified check to determine if the projectile is near the open sky.
        *   Updates `sky` to the maximum visibility found.
    3.  **Particle Emitter Control:**
        *   Finds the `ParticleEmitterComponent` associated with the projectile.
        *   Determines if the projectile is "safe" (i.e., `sky > safe_sky_min`).
        *   Checks if the projectile is "in hand" by looking for a `VariableStorageComponent`. This component is enabled only when the projectile is held by the player.
        *   Sets the `is_emitting` property of the `ParticleEmitterComponent` based on the `safe` status. If `safe` is true, particles are emitted; otherwise, they are not.
    4.  **Global Variable Update (When in Hand):**
        *   If the projectile is "in hand":
            *   If `safe` is true, sets the global variable `TOUCHING_GRASS` to "1".
            *   If `safe` is false, sets the global variable `TOUCHING_GRASS` to "0".

## Key Components and Globals

*   **`MagicConvertMaterialComponent`**: This component is likely responsible for material conversion effects. It is disabled by this script when the projectile is considered "touching grass."
*   **`ParticleEmitterComponent`**: Controls the emission of particles from the projectile. Its `is_emitting` property is dynamically controlled by the script.
*   **`VariableStorageComponent`**: Used as a flag to determine if the projectile is currently held by the player.
*   **`GlobalsGetValue("TOUCHING_GRASS")`**: Reads the global variable that indicates whether the player is considered to be "touching grass."
*   **`GlobalsSetValue("TOUCHING_GRASS", value)`**: Writes to the global variable `TOUCHING_GRASS`.
*   **`GameGetSkyVisibility(x, y)`**: A game function that returns a value indicating the visibility of the sky at a given coordinate.