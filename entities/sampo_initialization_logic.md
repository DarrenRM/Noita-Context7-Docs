---
title: Sampo Initialization Logic
category: entities
---

# Sampo Initialization Logic

This script defines the initialization logic for the "Sampo" entity in Noita, primarily focusing on dynamically setting its item name and description based on the number of orbs collected during the current run.

## Key Functionality

### Dynamic Item Naming

The script determines the `item_name` and `ui_description` for the Sampo based on the `GameGetOrbCountThisRun()` value.

*   **Orb Count Mapping:**
    *   If the orb count is less than 0, it's set to 0.
    *   If the orb count exceeds `MAX_ORB_NAMES` (13), it's capped at 13.
    *   The `item_name` and `ui_description` are constructed using a pattern like `$item_mcguffin_X` and `$itemdesc_mcguffin_X`, where `X` is the determined orb count.
*   **Special Case (33+ Orbs):**
    *   If `GameGetOrbCountThisRun()` is greater than 33, the Sampo will use the specific names `$item_mcguffin_33` and `$itemdesc_mcguffin_33`, regardless of the actual orb count beyond 33.

### Component Manipulation

The script interacts with specific entity components to apply these dynamic values.

*   **`ItemComponent`:**
    *   Retrieves the `ItemComponent` of the Sampo entity.
    *   Sets the `item_name` and `ui_description` properties of this component using the dynamically generated strings.
*   **`UIInfoComponent`:**
    *   Retrieves the `UIInfoComponent` of the Sampo entity.
    *   Sets the `name` property of this component to the dynamically generated `item_name`.

## Relevant Variables

*   `entity_id`: Stores the unique identifier for the Sampo entity.
*   `orb_count`: Stores the number of orbs collected in the current run, adjusted to be within a defined range.
*   `MAX_ORB_NAMES`: A constant defining the upper limit for the standard orb count mapping (set to 13).
*   `orb_name`: The dynamically generated string for the item's name.
*   `orb_desc`: The dynamically generated string for the item's description.

## Code Structure

```lua
-- todo - change the color of the sampo
local entity_id = GetUpdatedEntityID()
local orb_count = GameGetOrbCountThisRun()

local MAX_ORB_NAMES = 13

if( orb_count < 0 ) then orb_count = 0 end
if( orb_count > MAX_ORB_NAMES ) then orb_count = MAX_ORB_NAMES end

local orb_name = "$item_mcguffin_" .. tostring(orb_count)
local orb_desc = "$itemdesc_mcguffin_" .. tostring(orb_count)

if( GameGetOrbCountThisRun() > 33 ) then
	orb_name = "$item_mcguffin_33"
	orb_desc = "$itemdesc_mcguffin_33"
end

local item_component = EntityGetFirstComponent( entity_id, "ItemComponent" )
if( item_component ~= nil ) then
	ComponentSetValue( item_component, "item_name", orb_name )
	ComponentSetValue( item_component, "ui_description", orb_desc )
end

local uiinfo_component = EntityGetFirstComponent( entity_id, "UIInfoComponent" )
if( uiinfo_component ~= nil ) then
	ComponentSetValue( uiinfo_component, "name", orb_name )
end
```