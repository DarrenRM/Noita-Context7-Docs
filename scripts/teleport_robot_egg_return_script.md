---
title: Teleport Robot Egg Return Script
category: scripts
---

---

# Teleport Robot Egg Return Script

This script is designed to be attached to a "teleport robot" entity. Its primary function is to set the teleportation target of the robot to its original spawn location. This ensures that when the robot teleports, it returns to its starting point.

## Key Functionality

The script executes periodically to update the teleportation target.

### Core Logic

1.  **Initialization:**
    *   Includes necessary utility and portal summoning libraries.
    *   Retrieves the `entity_id` of the entity running this script.
    *   Finds the `TeleportComponent` associated with the entity.

2.  **Target Update:**
    *   If a `TeleportComponent` is found:
        *   It retrieves the original portal position using `get_portal_position()`.
        *   It then sets the `target` property of the `TeleportComponent` to these retrieved coordinates.

## Lua Code

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/biomes/summon_portal_util.lua")

-- this is called every x frames
local entity_id    = GetUpdatedEntityID()

local teleport_comp = EntityGetFirstComponentIncludingDisabled( entity_id, "TeleportComponent" )

-- sets teleporter target to original location
local portal_x, portal_y = get_portal_position()
if( teleport_comp ~= nil ) then
	ComponentSetValue2( teleport_comp, "target", portal_x, portal_y )
end
```

## Relevant Components

*   **`TeleportComponent`**: This is the core component that handles the teleportation logic. The script directly interacts with this component to set its `target` property.

## Notes

*   The frequency at which this script runs is determined by the entity's update rate, not explicitly defined within this script itself.
*   The `get_portal_position()` function is assumed to be defined in `data/scripts/biomes/summon_portal_util.lua` and returns the coordinates of the entity's original spawn point.