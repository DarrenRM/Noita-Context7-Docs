---
title: Laser Aim Perk
category: scripts/perks
---

# Laser Aim Perk

This script implements the "Laser Aim" perk in Noita, which causes a laser to be emitted from the player's wand when the perk is active.

## Functionality

The perk's primary function is to control the `LaserEmitterComponent` attached to the player's entity.

### Key Attributes/Elements

*   **`LaserEmitterComponent`**: This is the core component that enables laser emission. The script interacts with this component to toggle its `is_emitting` property.
*   **Wand Detection**: The script first checks if the player is holding a wand using `find_the_wand_held`.
*   **Laser Emission Logic**:
    *   If a wand is held, the `is_emitting` property of the `LaserEmitterComponent` is set to `true`.
    *   The laser's origin is adjusted slightly forward from the wand's position.
    *   If no wand is held, `is_emitting` is set to `false`, effectively disabling the laser.

## Code Structure

The script utilizes utility functions from `utilities.lua` and `gun_action_utils.lua`.

### Core Logic Flow

1.  **Get Player and Wand**: Obtain the player's entity ID and the ID of the wand they are currently holding.
2.  **Check for Wand**:
    *   If a wand is found:
        *   Retrieve the wand's transform (position and direction).
        *   Locate the `LaserEmitterComponent`.
        *   Enable laser emission by setting `is_emitting` to `true`.
        *   Adjust the laser's spawn position.
    *   If no wand is found:
        *   Locate the `LaserEmitterComponent`.
        *   Disable laser emission by setting `is_emitting` to `false`.