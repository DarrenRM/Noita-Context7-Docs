---
title: Forge Item Check Script
category: scripts
---

# Forge Item Check Script

This script handles the logic for checking and initiating the conversion of "forgeable" items within a Noita forge.

## Core Functionality

The primary purpose of this script is to:
*   Detect nearby entities tagged as "forgeable".
*   Verify that the detected item is not currently held in an inventory or wand.
*   If conditions are met, spawn a "forge_item_convert" entity to handle the actual conversion process.
*   Play a sound effect to indicate the conversion has started.
*   Prevent multiple conversions from starting simultaneously.

## Key Elements

### Entity Detection

*   **`EntityGetInRadiusWithTag(pos_x, pos_y, 40, "forgeable")`**: This function searches for entities within a 40-unit radius of the forge's position that possess the tag "forgeable".

### Item Validation

*   **`EntityGetRootEntity(id) == id`**: This crucial check ensures that the detected "forgeable" item is a standalone entity and not currently attached to another entity (like being carried in an inventory or a wand).

### Conversion Initiation

*   **`EntityLoad("data/entities/buildings/forge_item_convert.xml", pos_x, pos_y)`**: If a valid "forgeable" item is found, this line loads the entity responsible for the conversion process at the forge's location.
*   **`GamePlaySound("data/audio/Desktop/projectiles.snd", "projectiles/magic/create", pos_x, pos_y)`**: Plays a sound effect to provide auditory feedback that the conversion process has begun.

### Concurrency Control

*   **`if #EntityGetInRadiusWithTag(pos_x, pos_y, 10, "forge_item_convert") > 0 then return end`**: This check at the beginning of the script prevents a new conversion from starting if another "forge_item_convert" entity is already active within a 10-unit radius, thus avoiding duplicate conversions.

## Script Logic Flow

1.  Get the current entity ID and its position.
2.  Check if a conversion is already in progress nearby. If so, abort.
3.  Iterate through all entities within a 40-unit radius tagged as "forgeable".
4.  For each "forgeable" entity, check if it's a root entity (not carried).
5.  If a valid "forgeable" item is found:
    *   Load the `forge_item_convert.xml` entity.
    *   Play the "create" sound effect.
    *   Exit the script.