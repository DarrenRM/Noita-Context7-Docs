---
title: Sun Spot 1 Building Logic
category: scripts
---

# Sun Spot 1 Building Logic

This script defines the behavior for the "Sun Spot 1" building in Noita. Its primary function is to detect and initiate the conversion of "seed_a" entities into a processing state when they are within its vicinity.

## Key Functionality

*   **Entity Detection:** The script continuously checks for entities tagged with "seed_a" within a 64-unit radius of its own position.
*   **Conversion Trigger:** When a "seed_a" entity is found and is not currently being held in an inventory or wand (checked by `EntityGetRootEntity(id) == id`), the conversion process is initiated.
*   **Process Spawning:** A new entity, `spot_1_process.xml`, is loaded at the "seed_a" entity's location to handle the conversion.
*   **Parenting:** The newly spawned process entity is added as a child to the original "seed_a" entity.
*   **Sound Effect:** A "create" sound effect from the `projectiles/magic` category is played to indicate the start of the conversion.
*   **Abort Condition:** The script includes a check to prevent multiple conversion processes from starting simultaneously for the same area. If another "seed_a_process" entity is already active within a 64-unit radius, the script will abort.

## Important Variables

*   `entity_id`: The unique identifier for the Sun Spot 1 building entity.
*   `pos_x`, `pos_y`: The world coordinates of the Sun Spot 1 building.

## Dependencies

*   `data/scripts/lib/utilities.lua`
*   `data/scripts/gun/gun_actions.lua`

## Related Entities

*   `data/entities/buildings/sun/spot_1_process.xml`: The entity responsible for handling the conversion process.