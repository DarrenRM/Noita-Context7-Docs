---
title: Risky Critical Perk Logic
category: scripts
---

---

# Risky Critical Perk Logic

This script defines the behavior for the "Risky Critical" perk in Noita. It dynamically enables or disables a component tagged "risky_critical" based on the proximity of enemies.

## Core Functionality

The script checks for the presence of enemies within a specified radius around the player.

### Key Attributes

*   **`radius`**: Defines the detection radius for enemies. In this script, it's set to `56`.
*   **`"enemy"` tag**: Used to identify potential targets within the radius.
*   **`"risky_critical"` tag**: This tag is applied to the component that is enabled/disabled.

## Logic Flow

1.  **Get Player Position**: The script first obtains the player's current position (`x`, `y`).
2.  **Check for Enemies**: It then searches for entities with the `"enemy"` tag within the defined `radius`.
3.  **Check Component Status**: The script also checks if a component with the `"risky_critical"` tag is already present and enabled.
4.  **Enable Component**:
    *   If enemies are found (`#targets > 0`) AND the `"risky_critical"` component is NOT already enabled (`comp == nil`), the component is enabled.
5.  **Disable Component**:
    *   If NO enemies are found (`#targets == 0`) AND the `"risky_critical"` component IS currently enabled (`comp ~= nil`), the component is disabled.

## Code Structure

```lua
dofile_once("data/scripts/lib/utilities.lua")
dofile_once("data/scripts/gun/procedural/gun_action_utils.lua")

local entity_id = GetUpdatedEntityID()

local x,y = EntityGetTransform( entity_id )
local radius = 56 -- Detection radius for enemies

local targets = EntityGetInRadiusWithTag( x, y, radius, "enemy" )
local comp = EntityGetFirstComponent( entity_id, "ShotEffectComponent", "risky_critical" )

if ( #targets > 0 ) and ( comp == nil ) then
	-- Enable the component if enemies are present and it's not already enabled
	EntitySetComponentsWithTagEnabled( entity_id, "risky_critical", true )
elseif ( #targets == 0 ) and ( comp ~= nil ) then
	-- Disable the component if no enemies are present and it's currently enabled
	EntitySetComponentsWithTagEnabled( entity_id, "risky_critical", false )
end
```