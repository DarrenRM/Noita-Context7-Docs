---
title: Boss Ghost Helper Entity
category: entities
---

# Boss Ghost Helper Entity

This script manages the spawning of helper entities for the "Boss Ghost" in Noita. It ensures that a certain number of these helpers are present, spawning a new one if the count falls below the threshold.

## Core Functionality

The primary purpose of this script is to maintain a population of helper entities associated with the boss ghost.

### Key Attributes/Elements

*   **`EntityLoad`**: This function is used to spawn new entities into the game world.
*   **`GetUpdatedEntityID`**: Retrieves the unique identifier for the current entity being processed.
*   **`EntityGetTransform`**: Gets the position (x, y coordinates) of an entity.
*   **`EntityGetWithTag`**: Finds all entities in the game world that possess a specific tag.
*   **`boss_ghost_helper`**: The tag used to identify and count the helper entities.
*   **`ethereal_being.xml`**: The XML file defining the appearance and behavior of the helper entity that gets spawned.

## Logic Breakdown

1.  **Get Current Entity Information**: The script first obtains the `entity_id` and its `x`, `y` coordinates.
2.  **Count Existing Helpers**: It then searches for all entities tagged with `"boss_ghost_helper"`.
3.  **Check Population Threshold**: If the number of found helpers (`#help`) is less than 2, it proceeds to spawn a new one.
4.  **Spawn New Helper**: A new helper entity, defined by `data/entities/animals/ethereal_being.xml`, is loaded at the current entity's position (`x`, `y`).

## Example Usage (Conceptual)

This script would typically be attached to an entity that acts as the "manager" for the boss ghost's helpers. When the boss ghost is active, this manager entity would ensure its supporting entities are present.

```lua
-- This script is designed to be attached to an entity that manages boss_ghost_helper entities.
-- It's not meant to be called directly by the player or other game systems in isolation.

dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

-- Find all entities currently tagged as boss_ghost_helper
local help = EntityGetWithTag( "boss_ghost_helper" )

-- If there are fewer than 2 helpers, spawn a new one
if ( #help < 2 ) then
	EntityLoad( "data/entities/animals/ethereal_being.xml", x, y )
end
```