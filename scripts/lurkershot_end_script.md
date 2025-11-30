---
title: Lurkershot End Script
category: scripts/
---

# Lurkershot End Script

This script handles the final placement and activation of a "lurker" entity after it has been shot or launched. It determines the surface normal at the target location and adjusts the lurker's position to be flush with the surface before enabling its associated components.

## Key Functionality

*   **Entity Identification:** Retrieves the current entity's ID and its transform (position).
*   **Lurker ID Retrieval:** Accesses a `VariableStorageComponent` to get the ID of the lurker entity that was launched.
*   **Surface Normal Calculation:** Uses `GetSurfaceNormal` to find the normal vector and distance to the surface at the intended landing spot.
*   **Position Adjustment:** If a surface is detected, the lurker's position is adjusted to be precisely on the surface.
*   **Lurker Activation:** If the lurker entity is valid, its transform is set to the adjusted position, its transform is applied, and components tagged with "lurker_data" are enabled.

## Core Logic Breakdown

1.  **Initialization:**
    *   `dofile_once("data/scripts/lib/utilities.lua")`: Includes utility functions.
    *   `local entity_id = GetUpdatedEntityID()`: Gets the ID of the entity executing this script.
    *   `local x, y = EntityGetTransform( entity_id )`: Gets the current position of the entity.

2.  **Lurker Entity Retrieval:**
    *   `local comp = EntityGetFirstComponent( entity_id, "VariableStorageComponent", "lurker_id" )`: Searches for a `VariableStorageComponent` named "lurker\_id".
    *   `if ( comp ~= nil ) then ... end`: Proceeds only if the component is found.
    *   `local lurker_id = ComponentGetValue2( comp, "value_int" )`: Extracts the integer value (the lurker's entity ID) from the component.

3.  **Surface Detection and Positioning:**
    *   `local f, nx, ny, d = GetSurfaceNormal( x, y, 16, 8 )`: Calculates the surface normal.
        *   `x, y`: The point to check from.
        *   `16, 8`: Radii for surface detection.
    *   `if f then ... end`: Executes if a surface is found (`f` is true).
    *   `x = x - nx * d`: Adjusts the X-coordinate to be on the surface.
    *   `y = y - ny * d`: Adjusts the Y-coordinate to be on the surface.

4.  **Lurker Entity Application:**
    *   `local test = EntityGetTransform( lurker_id )`: Gets the transform of the lurker to check if it's a valid entity.
    *   `if ( lurker_id ~= nil ) and ( lurker_id ~= NULL_ENTITY ) and ( test ~= nil ) then ... end`: Ensures the lurker ID is valid and the entity exists.
    *   `EntitySetTransform( lurker_id, x , y )`: Sets the lurker's transform to the calculated surface position.
    *   `EntityApplyTransform( lurker_id, x, y )`: Applies the transform to the lurker entity.
    *   `EntitySetComponentsWithTagEnabled( lurker_id, "lurker_data", true )`: Enables all components on the lurker that have the tag "lurker\_data".