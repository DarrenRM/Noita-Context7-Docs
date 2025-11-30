---
title: Fungus Perk Initialization
category: scripts/perks
---

# Fungus Perk Initialization

This script handles the initialization logic for the "Fungus" perk in Noita. It primarily focuses on removing specific tags from the entity that has been granted this perk.

## Key Functionality

The core purpose of this script is to ensure that entities with the "Fungus" perk do not retain certain tags that might interfere with their intended behavior or interactions within the game.

### Tag Management

*   **`homing_target` Removal:** If the entity possesses the `homing_target` tag, it is removed. This suggests that the Fungus perk might alter how entities are targeted or interact with homing mechanics.
*   **`enemy` Removal:** If the entity possesses the `enemy` tag, it is also removed. This is a significant indicator that the Fungus perk might change the affiliation or behavior of the entity, potentially making it non-hostile or altering its role in combat.

## Script Logic

The script executes the following steps:

1.  **Include Utilities:** `dofile_once("data/scripts/lib/utilities.lua")` - Imports necessary utility functions.
2.  **Get Entity Information:**
    *   `local entity_id = GetUpdatedEntityID()` - Retrieves the unique identifier for the entity being processed.
    *   `local x, y = EntityGetTransform( entity_id )` - Gets the current position of the entity (though `x` and `y` are not used in this specific snippet).
3.  **Conditional Tag Removal:**
    *   `if EntityHasTag( entity_id, "homing_target" ) then EntityRemoveTag( entity_id, "homing_target" ) end` - Checks for and removes the `homing_target` tag.
    *   `if EntityHasTag( entity_id, "enemy" ) then EntityRemoveTag( entity_id, "enemy" ) end` - Checks for and removes the `enemy` tag.

## Implications for Modding

When creating mods that interact with or modify the Fungus perk, developers should be aware of these tag removals. This script might need to be considered or potentially modified if the mod aims to:

*   Change the targeting behavior of Fungus-affected entities.
*   Alter the combat role or affiliation of Fungus-affected entities.
*   Introduce new interactions with homing mechanics or enemy classifications.