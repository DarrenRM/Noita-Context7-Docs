---
title: Glue Projectile Initialization
category: scripts
---

# Glue Projectile Initialization

This script handles the initialization and targeting logic for glue projectiles in Noita. It determines which entities the glue should attach to, prioritizing the closest valid target and optionally a secondary target.

## Key Attributes and Logic

### Targeting Parameters

*   **`max_dist`**: The maximum distance (in pixels) a projectile can travel to find a target.
*   **`tag`**: The tag (`"hittable"`) used to identify entities that can be targeted by the glue.

### Initialization

1.  **Entity Setup**: Retrieves the current entity's ID and transform (position).
2.  **Anchor Positioning**: Iterates through child entities tagged as `"glue_anchor"` and sets their position to match the projectile's initial position.
3.  **Crowding Optimization**: If more than 10 entities with the `"glue"` tag are found within an 80-pixel radius, the projectile is killed to prevent performance issues.

### Primary Target Selection

1.  **Find Closest**: Searches for the closest entity with the `"hittable"` tag.
2.  **Validation**:
    *   Checks if a target was found.
    *   Ensures the target is the root entity.
    *   Verifies the target is within `max_dist`.
    *   Checks if the target has the tag `"glue_NOT"`, in which case it's ignored.
3.  **Assign Target**: If a valid primary target is found, its entity ID is stored in the `VariableStorageComponent` of the first child entity (assumed to be the primary glue anchor).

### Secondary Target Selection (Optional)

1.  **Check for Multiple Targets**: If fewer than two entities with the `"hittable"` tag are found within `max_dist`, no secondary target is assigned.
2.  **Random Selection**: If multiple targets exist, a random target is selected from the array of found targets.
3.  **Assign Secondary Target**: If the randomly selected target is different from the primary target, its entity ID is stored in the `VariableStorageComponent` of the second child entity (assumed to be the secondary glue anchor).

```lua
--[[
This script initializes glue projectiles, determining their targets.
It prioritizes the closest valid entity and can optionally target a second entity.
]]--

dofile_once("data/scripts/lib/utilities.lua")

local max_dist = 40 -- Maximum distance to find a target
local tag = "hittable" -- Tag for entities that can be targeted

local entity_id = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform(entity_id)

-- Set initial position for glue anchors
local children = EntityGetAllChildren(entity_id)
for _,anchor in ipairs(children) do
	if EntityHasTag(anchor, "glue_anchor") then
		EntitySetTransform(anchor, pos_x, pos_y)
	end
end

-- Optimization: remove if the area becomes too crowded with glue
if #EntityGetInRadiusWithTag( pos_x, pos_y, 80, "glue") > 10 then
	EntityKill(entity_id)
	return
end

-- Identify and validate the primary target
local target = EntityGetClosestWithTag( pos_x, pos_y, tag)
if target == nil or target == 0 then return end -- No target found

target = EntityGetRootEntity(target) -- Get the root entity of the target
local tx, ty = EntityGetTransform(target)
if get_distance(pos_x, pos_y, tx, ty) > max_dist or EntityHasTag( target, "glue_NOT" ) then return end -- Target too far or is explicitly not glueable

-- Assign the primary target to the first glue anchor's VariableStorageComponent
component_write( EntityGetFirstComponent( children[1], "VariableStorageComponent" ), { value_int = target } )

-- Optional: Identify and assign a secondary target
local targets = EntityGetInRadiusWithTag( pos_x, pos_y, max_dist, tag)
if #targets < 2 then return end -- Not enough targets for a secondary

SetRandomSeed(pos_x, pos_y + GameGetFrameNum()) -- Seed for random selection
local target2 = EntityGetRootEntity(random_from_array(targets)) -- Select a random target
if target2 ~= target then -- Ensure the secondary target is different from the primary
	-- Assign the secondary target to the second glue anchor's VariableStorageComponent
	component_write( EntityGetFirstComponent( children[2], "VariableStorageComponent" ), { value_int = target2 } )
end
```