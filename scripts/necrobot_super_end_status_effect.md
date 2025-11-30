---
title: Necrobot Super End Status Effect
category: scripts
---

# Necrobot Super End Status Effect

This script defines the behavior for a status effect that triggers when a "necrobot" entity is about to be destroyed. It spawns a mini-pit entity and a red poof particle effect at the necrobot's location, and then kills the necrobot itself.

## Key Components

### Entity Spawning

*   **`minipit.xml`**: A mini-pit entity is spawned at the necrobot's current position. This likely serves as a visual or gameplay consequence of the necrobot's demise.
*   **`poof_red_sparse.xml`**: A sparse red poof particle effect is spawned at the necrobot's current position, indicating a visual cue for the event.

### Entity Modification

*   **`VariableStorageComponent`**: Added to the spawned `minipit` entity.
    *   **`_tags="no_gold_drop"`**: This tag prevents the spawned mini-pit from dropping gold, ensuring a specific gameplay outcome.

### Entity Destruction

*   **`EntityKill( entity_id )`**: The original necrobot entity that triggered this status effect is immediately killed.

## Script Logic

The script first retrieves the ID and position of the entity that has this status effect applied. It then proceeds to load the specified entities and components, and finally terminates the original entity.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity_id )

local eid = EntityLoad( "data/entities/animals/special/minipit.xml", x, y )
EntityLoad( "data/entities/particles/poof_red_sparse.xml", x, y )
EntityAddComponent( eid, "VariableStorageComponent",
{
	_tags="no_gold_drop",
} )

EntityKill( entity_id )
```