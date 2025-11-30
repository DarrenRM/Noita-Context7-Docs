---
title: Null Room Check Success Script
category: scripts
---

---

# Null Room Check Success Script

This script defines the behavior for a successful check within a "null room" context in Noita. It's designed to be attached to an entity that signifies the completion of a specific check.

## Key Functionality

The primary function of this script is to add a specific tag to the entity it's attached to, indicating that the check has been successful.

### `material_area_checker_success( pos_x, pos_y )`

This function is called when the entity associated with this script has successfully passed a check.

*   **`pos_x`, `pos_y`**: These parameters represent the X and Y coordinates of the entity. While provided, they are not directly used within this specific function's logic.
*   **`entity_id = GetUpdatedEntityID()`**: Retrieves the unique identifier of the entity that triggered this function.
*   **`EntityAddTag( entity_id, "null_room_check" )`**: This is the core action. It adds the tag `"null_room_check"` to the entity. This tag can then be used by other game systems or scripts to identify entities that have passed this particular check.
*   **`if ( EntityHasTag( entity_id, "null_room_check" ) == false ) then ... end`**: This conditional check ensures that the tag is only added if it doesn't already exist. This prevents redundant tag additions.

## Usage

This script is typically used as a component of an entity that acts as a trigger or marker within a "null room" or similar game mechanic. When the conditions for success are met, this script's function is invoked, marking the entity with the `"null_room_check"` tag.