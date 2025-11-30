---
title: Boss Sky Damage Logic
category: entities
---

---

# Boss Sky Damage Logic

This script defines the damage mechanics for the "Boss Sky" entity in Noita. It calculates and applies holy damage to the player based on the player's current health percentage relative to a stored threshold.

## Key Functionality

### Player Health Threshold and Damage Application

The script dynamically determines the damage to inflict on the player. It compares the player's current health percentage against a stored `hp_percentage` value.

*   **Damage Calculation:** Damage is calculated as `max_hp * (player_hp_percentage - hp_percentage)`. This ensures that damage is only applied when the player's health percentage drops below the stored threshold.
*   **Minimum Damage:** The `math.max(0, ...)` ensures that no negative damage is applied.
*   **Damage Type:** The damage inflicted is `DAMAGE_HOLY`.
*   **Damage Source:** The damage is attributed to the player entity itself (`"$damage_holy"`).
*   **Visual Feedback:** A small red poof particle effect (`data/entities/particles/poof_red_tiny.xml`) is spawned at the player's location when damage is applied.

### Player Targeting and Positioning

The script attempts to position the "Boss Sky" entity relative to the player.

*   **Player Identification:** It first tries to get active player entities. If none are found, it looks for entities tagged as "polymorphed\_player".
*   **Entity Positioning:** If a player is found, the "Boss Sky" entity's transform is updated to be near the player's "cape\_root" hotspot, slightly above and to the right.

### Polymorphed Player Handling

If the player is polymorphed and no active players are found, the script ensures the "Boss Sky" entity has a limited lifetime.

*   **Lifetime Component:** It checks for a `LifetimeComponent` and sets its `kill_frame` to 90 frames from the current game frame. This prevents the entity from persisting indefinitely in this state.

## Key Components and Variables

*   **`entity_id`**: The unique identifier for the "Boss Sky" entity.
*   **`var`**: A `VariableStorageComponent` used to store the `hp_percentage` threshold.
*   **`hp_percentage`**: A float value representing the player's health percentage threshold. Damage is applied when the player's health falls below this value.
*   **`players`**: A table containing the IDs of the player entities.
*   **`player_id`**: The ID of the first player entity found.
*   **`px`, `py`, `ang`, `sx`, `sy`**: Player's transform properties.
*   **`hx`, `hy`**: Player's "cape\_root" hotspot coordinates.
*   **`tx`, `ty`**: Target coordinates for the "Boss Sky" entity.
*   **`DamageModelComponent`**: Component on the player entity used to read health information.
*   **`LifetimeComponent`**: Component on the "Boss Sky" entity used to manage its lifespan.

## Lua Snippets

```lua
-- Retrieve the entity's ID and initial transform
local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform( GetUpdatedEntityID() )

-- Access the VariableStorageComponent to get the HP percentage threshold
local var = EntityGetFirstComponent( entity_id, "VariableStorageComponent" )
local hp_percentage = 0
if var ~= nil then
	hp_percentage = ComponentGetValue2( var, "value_float" )
end

-- Get player entities
local players = get_players()
if #players == 0 then
	-- Handle polymorphed players
	players = EntityGetWithTag("polymorphed_player")
	if #players > 0 then
		local lifetime = EntityGetFirstComponent( entity_id, "LifetimeComponent" )
		if lifetime ~= nil then
			ComponentSetValue2( lifetime, "kill_frame", GameGetFrameNum() + 90 )
			return
		end
	end
end

-- If players are found, proceed with damage calculation and positioning
if #players > 0 then
	local player_id = players[1]
	local px, py, ang, sx, sy = EntityGetTransform( player_id  )

	-- Calculate target position based on player's hotspot
	local hx, hy = EntityGetHotspot( player_id, "cape_root", false )
	local tx, ty = px+hx, py+hy-2
	EntitySetTransform( entity_id, tx, ty )

	-- Read player's DamageModelComponent to get current and max HP
	component_read( EntityGetFirstComponent( player_id, "DamageModelComponent" ), { max_hp = 0, hp = 0 }, function(comp)
		local player_hp_percentage = comp.hp / comp.max_hp
		if player_hp_percentage >= hp_percentage then
			-- Calculate damage based on HP difference
			local damage = math.max( 0 , comp.max_hp * ( player_hp_percentage - hp_percentage ) );
			if damage > 0 then
				-- Inflict holy damage and spawn particle effect
				EntityInflictDamage( player_id, damage, "DAMAGE_HOLY", "$damage_holy", "NONE", 0, 0, NULL_ENTITY )
				EntityLoad( "data/entities/particles/poof_red_tiny.xml", tx, ty )
			end
		end
	end)
end
```