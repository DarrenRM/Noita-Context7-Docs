---
title: Pata Activation Script
category: scripts
---

# Pata Activation Script

This script defines the behavior for activating a "pata" (likely a mechanism or entity) when it receives damage.

## Function: `damage_received`

This function is triggered when the entity associated with this script takes damage.

### Key Actions:

*   **Get Entity ID:** Retrieves the unique identifier of the entity that received damage.
*   **Get Entity Position:** Obtains the `x` and `y` coordinates of the damaged entity.
*   **Enable "pata_active" Components:** Activates all components within the entity that have the tag "pata_active". This likely signifies the entity entering an active state.
*   **Disable "pata_inactive" Components:** Deactivates all components within the entity that have the tag "pata_inactive". This likely signifies the entity exiting an inactive state.

### Lua Code:

```lua
dofile_once("data/scripts/lib/utilities.lua")

function damage_received()
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )

	EntitySetComponentsWithTagEnabled( entity_id, "pata_active", true )
	EntitySetComponentsWithTagEnabled( entity_id, "pata_inactive", false )
end
```