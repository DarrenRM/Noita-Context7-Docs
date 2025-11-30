---
title: Pebble Spawn Script
category: scripts
---

# Pebble Spawn Script

This script is responsible for spawning a "pebble" entity at the current location, with a slight adjustment based on the surface normal.

## Key Functionality

The primary purpose of this script is to instantiate `pebble_physics.xml` at a calculated position.

### Entity Spawning

*   **`EntityLoad( "data/entities/animals/pebble_physics.xml", offsetx, offsety )`**: This is the core function that loads and places the `pebble_physics.xml` entity.

### Position Calculation

The script attempts to find the surface normal at the entity's current position to adjust the spawn point.

*   **`GetSurfaceNormal( x, y, 5, 16 )`**: This function attempts to find the surface normal.
    *   The parameters `5` and `16` likely define the search radius and maximum distance for finding the normal.
*   **`offsetx`, `offsety`**: These variables store the calculated spawn coordinates. If a surface normal is found, the spawn point is adjusted slightly away from the surface.

## Important Attributes

*   **`entity_id`**: Retrieves the unique identifier for the current entity.
*   **`x`, `y`**: Stores the current transform (position) of the entity.
*   **`normalfound`**: A boolean indicating whether a surface normal was successfully detected.
*   **`normalx`, `normaly`**: The components of the detected surface normal vector.
*   **`normaldist`**: The distance along the normal to the surface.

## Dependencies

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: This line ensures that utility functions are loaded and available.