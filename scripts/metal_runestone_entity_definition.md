---
title: Metal Runestone Entity Definition
category: scripts
---

# Metal Runestone Entity Definition

This script defines the behavior and appearance of the Metal Runestone entity in Noita.

## Core Functionality

The primary function of this script is to load the `runestone_metal.xml` entity definition at the runestone's position. This XML file contains the visual representation, collision properties, and other fundamental aspects of the Metal Runestone.

## Key Attributes/Elements

*   **`EntityLoad`**: This is the core function called to instantiate the Metal Runestone. It takes the path to the entity's XML definition and its world coordinates.
*   **`data/entities/misc/runestone_metal.xml`**: This is the specific entity definition file that dictates the Metal Runestone's properties.

## Script Logic

The script performs the following actions:

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Ensures that utility functions are loaded and available.
2.  **`local entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity being processed.
3.  **`local x, y = EntityGetTransform( entity_id )`**: Gets the world coordinates (x, y) of the entity.
4.  **`EntityLoad( "data/entities/misc/runestone_metal.xml", x, y )`**: Loads the Metal Runestone entity from its XML definition at the determined coordinates.

## Related Files

*   `data/entities/misc/runestone_metal.xml`: Contains the detailed definition of the Metal Runestone entity.