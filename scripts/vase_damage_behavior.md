---
title: Vase Damage Behavior
category: scripts
---

# Vase Damage Behavior

This script defines the behavior of a vase when it receives damage.

## Core Functionality

The primary function `damage_received` is triggered when the vase takes damage.

### Key Attributes & Elements

*   **`damage_received( damage, desc, entity_who_caused, is_fatal )`**: The main function that handles incoming damage.
    *   `damage`: The amount of damage received.
    *   `desc`: A description of the damage source.
    *   `entity_who_caused`: The entity that inflicted the damage.
    *   `is_fatal`: A boolean indicating if the damage is fatal.

### Behavior on Damage

When the vase receives damage:

1.  It retrieves its own entity ID and position.
2.  It sets a random seed based on game frame and position for deterministic randomness.
3.  It checks if the damage was self-inflicted; if so, it returns.
4.  It spawns **4** `longleg.xml` entities around the vase's position. The exact spawn location is randomized within a small radius.

```lua
function damage_received( damage, desc, entity_who_caused, is_fatal )
	-- print("damage")
	local entity_id = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

	if( entity_who_caused == entity_id ) then return end

	for i=1,4 do
		local e = EntityLoad( "data/entities/animals/longleg.xml", pos_x + Random(-10, 10), pos_y + Random(-10, 10))
	end
end
```