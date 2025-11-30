---
title: Spells to Power Tag
category: scripts
---

# Spells to Power Tag

This script adds the `spells_to_power_target` tag to the root entity when a projectile with this script is fired. This tag is likely used by other game systems to identify projectiles that are part of the "Spells to Power" mechanic.

## Key Functionality

*   **Tagging the Root Entity:** The primary function is to ensure the root entity of the projectile possesses the `spells_to_power_target` tag.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Includes utility functions.

local entity_id = GetUpdatedEntityID() -- Gets the ID of the current entity (the projectile).
local root_id = EntityGetRootEntity( entity_id ) -- Gets the ID of the root entity associated with the projectile.
local x, y = EntityGetTransform( entity_id ) -- Retrieves the projectile's position (though not used in this specific logic).
local radius = 160 -- Defines a radius, also not directly used in the tagging logic.

-- Checks if the root entity already has the "spells_to_power_target" tag.
if ( EntityHasTag( root_id, "spells_to_power_target" ) == false ) then
	-- If the tag is not present, it's added to the root entity.
	EntityAddTag( root_id, "spells_to_power_target" )
end
```