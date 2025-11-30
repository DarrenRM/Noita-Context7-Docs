---
title: Lurker Shot Initialization Script
category: scripts
---

---

# Lurker Shot Initialization Script

This script handles the initialization of a projectile fired by a "lurker" enemy in Noita. It's responsible for setting up the projectile's initial state and linking it back to its originating entity.

## Core Functionality

The primary function `shot(proj_id)` is called when a lurker's projectile is created.

### Key Actions:

*   **Disable Lurker Data:** The script first disables components with the tag "lurker_data" on the projectile's originating entity. This likely prevents the lurker from re-firing immediately or performing other actions while its projectile is active.
*   **Store Projectile Origin:** It retrieves a `VariableStorageComponent` from the projectile (`proj_id`) that is specifically tagged with "lurkershot_id".
*   **Link Projectile to Source:** If the "lurkershot_id" component is found, its value is set to the `entity_id` of the projectile itself. This establishes a link, allowing the projectile to potentially reference its source entity later.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")

function shot( proj_id )
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	-- Disable components related to the lurker's firing mechanism
	EntitySetComponentsWithTagEnabled( entity_id, "lurker_data", false )
	
	-- Find the variable storage component on the projectile
	local comp = EntityGetFirstComponent( proj_id, "VariableStorageComponent", "lurkershot_id" )
	if ( comp ~= nil ) then
		-- Store the projectile's entity ID in the variable storage
		ComponentSetValue2( comp, "value_int", entity_id )
	end
end
```