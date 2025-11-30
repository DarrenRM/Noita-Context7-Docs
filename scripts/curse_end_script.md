---
title: Curse End Script
category: scripts/
---

# Curse End Script

This script handles the removal of the "effect_CURSE" tag from an entity, effectively ending a curse effect.

## Core Functionality

The script identifies the root entity associated with the current entity and checks if it possesses the "effect_CURSE" tag. If the tag is present, it is removed.

### Key Attributes/Elements

*   **`entity_id`**: Represents the unique identifier of the entity being processed.
*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered this script.
*   **`EntityGetRootEntity( entity_id )`**: Gets the root entity of the provided entity. This is important as curse effects might be applied to a root entity.
*   **`EntityHasTag( entity_id, "effect_CURSE" )`**: Checks if the specified entity has the "effect_CURSE" tag.
*   **`EntityRemoveTag( entity_id, "effect_CURSE" )`**: Removes the "effect_CURSE" tag from the specified entity.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
entity_id = EntityGetRootEntity( entity_id )

local curseflag = EntityHasTag( entity_id, "effect_CURSE" )

if curseflag then
	EntityRemoveTag( entity_id, "effect_CURSE" )
end
```