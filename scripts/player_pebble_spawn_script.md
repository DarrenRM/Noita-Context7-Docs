---
title: Player Pebble Spawn Script
category: scripts
---

# Player Pebble Spawn Script

This script handles the spawning of a "pebble" entity, typically used for player projectiles, at a calculated position.

## Core Functionality

The primary purpose of this script is to:
1.  Get the current entity's ID and transform (position).
2.  Calculate a surface normal to determine the ground's orientation.
3.  Adjust the spawn position based on the surface normal to ensure the pebble spawns correctly on slopes.
4.  Load the `pebble_player_physics.xml` entity at the calculated position.

## Key Attributes and Elements

### Entity Loading

*   **`EntityLoad( "data/entities/projectiles/deck/pebble_player_physics.xml", offsetx, offsety )`**: This is the core function that instantiates the pebble projectile.
    *   The first argument specifies the XML file defining the pebble entity.
    *   `offsetx` and `offsety` are the calculated coordinates where the entity will be placed.

### Surface Normal Calculation

*   **`GetSurfaceNormal( x, y, 5, 16 )`**: This function attempts to find the surface normal at the entity's current position.
    *   `x`, `y`: The starting coordinates for the raycast.
    *   `5`: The maximum distance to search downwards for a surface.
    *   `16`: The maximum distance to search sideways for a surface.
    *   Returns `normalfound` (boolean), `normalx` (x-component of the normal), `normaly` (y-component of the normal), and `normaldist` (distance to the surface).

### Position Adjustment

*   **`if normalfound then ... end`**: This block executes only if a surface normal was successfully found.
    *   **`offsetx = offsetx + normalx * (0 - math.abs(normaldist))`**: Adjusts the x-coordinate of the spawn point. The adjustment is proportional to the normal's x-component and the distance to the surface, ensuring the pebble is placed "on" the surface.
    *   **`offsety = offsety + normaly * (0 - math.abs(normaldist))`**: Adjusts the y-coordinate of the spawn point similarly.

## Dependencies

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, likely including `GetUpdatedEntityID` and `EntityGetTransform`.

## Example Usage (Conceptual)

This script would typically be attached to an entity that triggers the spawning of a player projectile, such as a weapon or a special ability. When the trigger occurs, this script runs, calculates the appropriate spawn location, and then loads the pebble projectile entity.