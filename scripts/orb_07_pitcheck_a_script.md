---
title: Orb 07 Pitcheck A Script
category: scripts
---

# Orb 07 Pitcheck A Script

This script defines the behavior for an entity tagged as `orb_07_pitcheck_a`. Its primary function is to disable entities tagged with `pitcheck_b` when a collision is detected.

## Core Functionality

### `collision_trigger()`

This function is executed when the entity associated with this script experiences a collision.

*   **Purpose:** To identify and disable other entities in the game world.
*   **Mechanism:**
    1.  Retrieves the `entity_id` of the entity that triggered the collision.
    2.  Gets the current `x` and `y` coordinates of the triggering entity.
    3.  Searches for all entities in the game world that have the tag `"pitcheck_b"`.
    4.  Iterates through the found entities tagged with `"pitcheck_b"`.
    5.  For each found entity, it disables all components tagged with `"disabled"`.

## Key Elements

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, though none are directly used in the provided `collision_trigger` function.
*   **`GetUpdatedEntityID()`**: A Noita API function to get the ID of the entity that is currently being updated (in this case, the one that collided).
*   **`EntityGetTransform( entity_id )`**: A Noita API function to retrieve the position (`x`, `y`) of an entity.
*   **`EntityGetWithTag( "pitcheck_b" )`**: A Noita API function to find all entities that possess the specified tag.
*   **`EntitySetComponentsWithTagEnabled( v, "disabled", true )`**: A Noita API function used to enable or disable components of an entity. Here, it's used to *enable* the `"disabled"` tag, effectively disabling the entity's components.

## Usage Context

This script is likely part of a larger system involving "orbs" or specific environmental triggers within Noita. The `pitcheck_a` and `pitcheck_b` tags suggest a paired mechanism where one entity's activation (collision) leads to the deactivation or alteration of another. This could be used for:

*   Activating/deactivating traps.
*   Controlling the state of specific environmental hazards.
*   Implementing puzzle mechanics where one object's presence affects another.