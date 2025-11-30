---
title: Tentacle Boss Entity Configuration
category: entities
---

# Tentacle Boss Entity Configuration

This document describes the configuration for a tentacle entity, likely part of a boss encounter in Noita.

## Core Entity Properties

This section highlights key properties that define the tentacle's behavior and appearance.

### Transform and Movement

*   **`EntitySetTransform( entity_id, x, y, a )`**: This function is used to update the entity's position and rotation.
    *   `entity_id`: The unique identifier for the tentacle entity.
    *   `x`, `y`: The world coordinates of the tentacle.
    *   `a`: The rotation angle of the tentacle.

### Dynamic Angle Calculation

The tentacle's angle (`a`) is dynamically calculated based on the game's frame number, creating a subtle oscillating movement.

*   **`arc = 0.15`**: Defines the maximum amplitude of the oscillation.
*   **`angle = ( GameGetFrameNum() + 100 ) * 0.01`**: Calculates a base angle that increases over time.
*   **`a = math.cos( angle ) * arc`**: Applies a cosine function to the calculated angle, scaled by the `arc` value, to create a smooth, back-and-forth rotation.

## Scripting Dependencies

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: This line ensures that the `utilities.lua` script is loaded and executed only once, providing access to various helper functions.

## Key Functions Used

*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity being processed.
*   **`EntityGetTransform( entity_id )`**: Gets the current transform (position and rotation) of the specified entity.
*   **`EntitySetTransform( entity_id, x, y, a )`**: Sets the transform of the specified entity.
*   **`GameGetFrameNum()`**: Returns the current frame number of the game.
*   **`math.cos( angle )`**: Calculates the cosine of an angle.