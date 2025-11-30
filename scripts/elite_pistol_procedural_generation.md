---
title: Elite Pistol Procedural Generation
category: scripts
---

# Elite Pistol Procedural Generation

This script defines the procedural generation logic for an "Elite Pistol" in Noita. It dynamically adjusts various gun properties based on random chance and its rarity.

## Key Attributes and Modifications

The `generate_gun` function is the core of this script. It retrieves the entity's ID and transform, then uses these to set a random seed for consistent generation at a given location.

### Rarity and its Effects

*   **Rarity Check:** A 1 in 20 chance (`D(20) == 1`) determines if the pistol is considered "rare".
*   **Reload Time:** If rare, the reload time is halved.
*   **Light Color:** Rare pistols have their light component's color set to a distinct purple (`r: 128, g: 0, b: 255`).

### Gun Configuration Adjustments

The script modifies several properties within the `AbilityComponent`'s `gun_config`:

*   **Actions Per Round:** Fixed to `1` to ensure a more consistent firing behavior, rather than a "machinegunny" feel.
*   **Reload Time:** Calculated as `110 - 5 * D(10)`. This means the base reload time is between 60 and 105 frames, with rare pistols having half of that.
*   **Gun Name:** If a `gun_names` table is available globally, a random name from it is prepended to the pistol's existing UI name.

### Bullet Actions

The following bullet actions are added to the pistol:

*   `LIGHT_BULLET_TIMER`
*   `Y_SHAPE`
*   `BULLET`
*   `BULLET`

### Light Component

If the pistol is rare, its `LightComponent` properties are updated:

*   `update_properties`: Set to `1` to ensure changes are applied.
*   `r`, `g`, `b`: Set to `128`, `0`, `255` respectively, creating a purple light.

## Code Structure

```lua
-- Includes utility functions for gun generation
dofile('data/scripts/gun/procedural/gun_utilities.lua')

function generate_gun()
	-- Get entity ID and position for random seeding
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	SetRandomSeed( x, y )

	-- Check for AbilityComponent and determine rarity
	local ability_comp = EntityGetFirstComponent( entity_id, "AbilityComponent" )
	local is_rare = 0
	if( D(20) == 1 ) then is_rare = 1 end

	if( ability_comp ~= nil ) then
		-- Retrieve and modify gun configuration
		local actions = ComponentObjectGetValue( ability_comp, "gun_config", "actions_per_round" )
		local reload = ComponentObjectGetValue( ability_comp, "gun_config", "reload_time" )

		actions = 1 -- Fixed for consistent firing

		-- Calculate reload time with rarity modifier
		reload = 110 - 5 * D(10)
		if( is_rare == 1 ) then reload = reload * 0.5 end

		-- Modify gun name if global names exist
		local name = ComponentGetValue( ability_comp, "ui_name" )
		if( gun_names ~= nil ) then
			local rand_i = Random( 1, #gun_names )
			name = gun_names[ Random( 1, #gun_names ) ] .. ' ' .. name
		end

		-- Add bullet actions
		AddGunAction( entity_id, "LIGHT_BULLET_TIMER" )
		AddGunAction( entity_id, "Y_SHAPE" )
		AddGunAction( entity_id, "BULLET" )
		AddGunAction( entity_id, "BULLET" )

		-- Update component values
		ComponentSetValue( ability_comp, "ui_name", name )
		ComponentObjectSetValue( ability_comp, "gun_config", "actions_per_round", actions )
		ComponentObjectSetValue( ability_comp, "gun_config", "reload_time", reload )
	end

	-- Set light color for rare pistols
	if( is_rare == 1 ) then
		local light_comp = EntityGetFirstComponent( entity_id, "LightComponent" )
		if( light_comp ~= nil ) then
			ComponentSetValue( light_comp, "update_properties", 1)
			ComponentSetValue( light_comp, "r", 128 )
			ComponentSetValue( light_comp, "g", 0 )
			ComponentSetValue( light_comp, "b", 255 )
		end
	end
end

-- Execute the generation function
generate_gun()
```