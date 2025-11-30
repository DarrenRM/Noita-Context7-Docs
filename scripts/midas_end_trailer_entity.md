---
title: Midas End Trailer Entity
category: scripts
---

# Midas End Trailer Entity

This script is responsible for loading the `midas_end.xml` entity at the current position. This is likely used to trigger a specific visual or gameplay event during a trailer sequence.

## Core Functionality

The script performs the following actions:

1.  **Get Updated Entity ID**: Retrieves the unique identifier for the entity executing this script.
2.  **Get Entity Position**: Determines the current X and Y coordinates of the entity.
3.  **Load Trailer Entity**: Instantiates the `midas_end.xml` entity at the retrieved position.

## Key Elements

*   **`GetUpdatedEntityID()`**: A standard Noita API function to get the current entity's ID.
*   **`EntityGetTransform( entity_id )`**: Retrieves the position (X, Y) of the specified entity.
*   **`EntityLoad( entity_path, pos_x, pos_y )`**: Loads a new entity from the specified XML file path at the given coordinates.
    *   **`entity_path`**: `"data/entities/trailer/midas_end.xml"` - The path to the trailer-specific entity definition.
    *   **`pos_x`, `pos_y`**: The coordinates where the `midas_end.xml` entity will be spawned.

## Usage Context

This script is typically called from within a larger trailer sequence or event system in Noita, designed to visually represent the "Midas End" scenario. It's a simple loader script, with the actual visual and behavioral logic residing within the `midas_end.xml` entity.