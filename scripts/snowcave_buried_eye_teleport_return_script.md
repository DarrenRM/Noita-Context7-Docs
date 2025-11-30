---
title: Snowcave Buried Eye Teleport Return Script
category: scripts
---

# Snowcave Buried Eye Teleport Return Script

This script manages the teleportation behavior for the "Buried Eye" entity within the Snowcave biome in Noita. It specifically handles returning the player to a predefined location after interacting with the teleport.

## Key Functionality

The primary purpose of this script is to:

1.  **Retrieve Teleport Component:** It finds the `TeleportComponent` associated with the entity.
2.  **Determine Return Coordinates:** It fetches the default return coordinates for the teleport. These coordinates can be overridden by global variables.
3.  **Update Teleport Target:** It sets the `target` property of the `TeleportComponent` to the determined return coordinates, ensuring the player teleports to the correct location.

## Core Logic

The script executes periodically (every `x` frames) to ensure the teleport's return destination is correctly configured.

```lua
-- this is called every x frames
local entity_id    = GetUpdatedEntityID()

local teleport_comp = EntityGetFirstComponentIncludingDisabled( entity_id, "TeleportComponent" )

local teleport_back_x = 190
local teleport_back_y = 3080

-- get the defaults from teleport_comp(s)
if( teleport_comp ~= nil ) then
	teleport_back_x, teleport_back_y = ComponentGetValue2( teleport_comp, "target" )
	-- print( "teleport std pos:" .. teleport_back_x .. ", " .. teleport_back_y )
end

-- Override with global values if they exist
teleport_back_x = tonumber( GlobalsGetValue( "TELEPORT_SNOWCAVE_BURIED_EYE_POS_X", teleport_back_x ) )
teleport_back_y = tonumber( GlobalsGetValue( "TELEPORT_SNOWCAVE_BURIED_EYE_POS_Y", teleport_back_y ) )

-- Update the teleport component with the final coordinates
if( teleport_comp ~= nil ) then
	ComponentSetValue2( teleport_comp, "target", teleport_back_x, teleport_back_y )
	-- ComponentGetValue2( teleport_comp, "target.y", teleport_back_y ) -- commented out, likely for debugging
end
```

## Key Components and Variables

*   **`entity_id`**: The unique identifier for the entity running this script.
*   **`teleport_comp`**: A reference to the `TeleportComponent` attached to the entity. This component handles the actual teleportation logic.
*   **`teleport_back_x`, `teleport_back_y`**: Variables storing the X and Y coordinates for the teleport's return destination.
    *   Default values are `190` and `3080` respectively.
    *   These can be overridden by global variables:
        *   `TELEPORT_SNOWCAVE_BURIED_EYE_POS_X`
        *   `TELEPORT_SNOWCAVE_BURIED_EYE_POS_Y`
*   **`GetUpdatedEntityID()`**: A Noita API function to get the ID of the entity that triggered the script update.
*   **`EntityGetFirstComponentIncludingDisabled( entity_id, "TeleportComponent" )`**: Retrieves the `TeleportComponent` from the entity.
*   **`ComponentGetValue2( teleport_comp, "target" )`**: Reads the current target coordinates from the `TeleportComponent`.
*   **`GlobalsGetValue( key, default_value )`**: Retrieves a value from the global game state, using a default if the key is not found.
*   **`ComponentSetValue2( teleport_comp, "target", x, y )`**: Sets the target coordinates for the `TeleportComponent`.

## AI Modding Considerations

When modifying this script for AI-assisted modding:

*   **Teleport Destination:** The most common modification would be to change the `teleport_back_x` and `teleport_back_y` values, either directly or by influencing the global variables.
*   **Conditional Teleportation:** Advanced AI could potentially influence *when* this teleport is activated or *if* it targets the player, by manipulating the `TeleportComponent`'s properties or the entity's state.
*   **Global Variable Management:** Understanding how global variables are used to configure game elements is crucial for creating consistent and predictable AI behavior.