---
title: Essence to Power Cooldown Script
category: scripts
---

---

# Essence to Power Cooldown Script

This script handles the cooldown mechanism for the "Essence to Power" functionality in Noita. It primarily focuses on removing a specific tag from entities to reset or manage this cooldown.

## Core Functionality

The script's main purpose is to ensure that when an entity associated with the "essence_to_power_target" tag is processed, this tag is removed. This effectively resets the cooldown or prevents the effect from being reapplied until the tag is reacquired.

### Key Actions

*   **Get Entity Information:** Retrieves the current entity's ID, its root entity's ID, and its position.
*   **Tag Removal (Current Entity):** Checks if the current entity has the `"essence_to_power_target"` tag. If it does, the tag is removed.
*   **Tag Removal (Root Entity):** Checks if the root entity associated with the current entity has the `"essence_to_power_target"` tag. If it does, the tag is removed.

## Script Logic

The script executes a simple conditional check. It first targets the projectile or entity that triggered the script. If that entity possesses the `"essence_to_power_target"` tag, it's removed. Subsequently, it checks the root entity of the current entity. If the root entity also has this tag, it's removed as well. This dual removal ensures the cooldown is properly managed at both the projectile and the source entity level.

```lua
-- Retrieves the ID of the entity that triggered this script.
local entity_id = GetUpdatedEntityID()
-- Retrieves the root entity ID associated with the current entity.
local root_id = EntityGetRootEntity( entity_id )
-- Gets the X and Y coordinates of the entity.
local x, y = EntityGetTransform( entity_id )
-- Defines a radius, though not directly used in the current logic.
local radius = 160

-- Checks if the current entity has the "essence_to_power_target" tag.
if EntityHasTag( entity_id, "essence_to_power_target" ) then
	-- If the tag exists, it is removed from the current entity.
	EntityRemoveTag( entity_id, "essence_to_power_target" )
end

-- Checks if the root entity has the "essence_to_power_target" tag.
if EntityHasTag( root_id, "essence_to_power_target" ) then
	-- If the tag exists, it is removed from the root entity.
	EntityRemoveTag( root_id, "essence_to_power_target" )
end
```