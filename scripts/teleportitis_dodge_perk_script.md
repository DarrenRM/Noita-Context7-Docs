---
title: Teleportitis Dodge Perk Script
category: scripts
---

# Teleportitis Dodge Perk Script

This script defines the behavior for the "Teleportitis Dodge" perk in Noita. When an enemy projectile is detected within a certain range, the player character teleports away from the projectile's path.

## Key Attributes

*   **`sensor_range`**: The radius around the player within which enemy projectiles are detected.
*   **`teleport_range`**: The maximum distance the player will teleport.
*   **`time_active`**: The number of frames the perk's visual effects are active when not on cooldown.
*   **`time_cooldown`**: The number of frames the perk remains on cooldown after a successful dodge.

## Core Functionality

### `teleport(from_x, from_y, to_x, to_y)`

This function handles the actual teleportation process.

*   **Entity Movement**: Moves the player's root entity to the target coordinates (`to_x`, `to_y`).
*   **Visual Effects**: Spawns `teleportation_source.xml` and `teleportation_target.xml` particle effects at the origin and destination, respectively.
*   **Audio**: Plays the "misc/teleport_use" sound effect.
*   **Environment Modification**: Creates a small hole in the environment at the teleport destination using `teleportitis_dodge_hole.png` to prevent the player from getting stuck.

### `set_cooldown(on_cooldown, frames)`

Manages the perk's cooldown state and associated visual effects.

*   **VFX Control**: Enables or disables the "teleportitis\_dodge\_vfx" component based on the `on_cooldown` parameter.
*   **Script Execution Timing**: Adjusts the `execute_every_n_frame` and `mNextExecutionTime` of the perk's script component to control its activation frequency.

## Detection and Teleport Logic

The script iterates through entities within the `sensor_range` that have the "projectile" tag.

1.  **Projectile Identification**: It checks if the detected entity is indeed a projectile and retrieves its `ProjectileComponent`.
2.  **Shooter Check**: It verifies that the projectile was not shot by the player themselves.
3.  **Teleport Direction Calculation**:
    *   It reads the player's aiming reticle to determine the aiming direction.
    *   This direction is normalized and scaled by `teleport_range`.
    *   The direction is then rotated 90 degrees towards the top, relative to the player's aim.
    *   A `RaytracePlatforms` is performed to find a valid teleport destination, adjusting the target position if a platform is hit.
4.  **Position Adjustment**: The calculated teleport position is adjusted backward slightly (up to 20 pixels) to reduce the chance of teleporting into solid objects.
5.  **Teleport Execution**: If a valid teleport destination is found, the `teleport` function is called, and the perk is set to cooldown using `set_cooldown(true, time_cooldown)`.

## Cooldown Reset

If no enemy projectiles are detected within the `sensor_range` during a script execution, the perk's cooldown is reset, and its visual effects are managed by `set_cooldown(false, time_active)`.