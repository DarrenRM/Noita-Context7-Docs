---
title: Greed Curse Biome Check
category: scripts
---

# Greed Curse Biome Check

This script manages the behavior of the "Greed Curse" based on the player's current biome and depth. It determines when the curse should appear, disappear, and how it's visually represented.

## Core Logic

The script primarily tracks the `status` of the curse and a `timer`.

*   **Status 0:** The curse is inactive or has been removed.
*   **Status 1:** The curse is active and will attempt to return if conditions are met.

The curse's behavior is tied to specific biomes and depth changes.

## Key Variables and Components

The script interacts with several `VariableStorageComponent` variables to maintain its state:

*   **`status`**: An integer representing the current state of the curse (0 for inactive, 1 for active).
*   **`latest_depth`**: Stores the depth at which the curse was last active or removed. Used to prevent immediate re-activation.
*   **`timer`**: A counter used to delay the curse's return after it has been removed.

## Biome and Depth Detection

The script continuously checks the player's current biome and depth:

*   **`biome`**: Retrieves the name of the current biome using `BiomeMapGetName()`.
*   **`depth`**: Calculates the current depth based on the player's Y-coordinate.
*   **`depth_remainder`**: The remaining Y-coordinate within the current depth segment, used for finer-grained checks.

## Curse Activation and Deactivation

### Deactivation Conditions

The curse is deactivated (status set to 0) when:

*   The player is *not* in a "holymountain" or "victoryroom" biome.
*   The player enters a "holymountain" or "victoryroom" biome *from a lower depth* and the `depth_remainder` is sufficiently large (greater than 150).
*   The `greed_curse_gone` game flag is *not* set.

Upon deactivation:

*   The "curse" tag is disabled for the entity.
*   An important game message is displayed indicating the curse has gone.
*   `latest_depth` is updated to the current depth.

### Activation Conditions

The curse attempts to return (status set to 1) when:

*   The `status` is currently 1 (meaning it's trying to return).
*   The `greed_curse_gone` game flag is *not* set.
*   The `timer` has reached 5.

When the timer reaches 5:

*   A game message is displayed indicating the curse's return.
*   The "curse" tag is enabled for the entity.
*   The timer is set to 6 to prevent immediate re-triggering.

## Timer Logic

The `timer` variable is incremented each frame as long as:

*   The `status` is 1.
*   The `timer` is less than 5.
*   The `greed_curse_gone` game flag is *not* set.

This creates a 5-frame delay before the curse attempts to return after being removed.

## Game Flags

*   **`greed_curse_gone`**: This flag is checked to determine if the curse has been permanently removed by game progression. If this flag is set, the curse will not reappear.

## Entity Management

The script operates on an entity identified by `GetUpdatedEntityID()`. It reads and writes to `VariableStorageComponent`s attached to this entity to maintain its state across game ticks.

```lua
-- Example of reading a VariableStorageComponent value
local comps = EntityGetComponent( entity_id, "VariableStorageComponent" )
if ( comps ~= nil ) then
	for i,comp in ipairs( comps ) do
		local name = ComponentGetValue2( comp, "name" )
		if ( name == "status" ) then
			status = ComponentGetValue2( comp, "value_int" )
			scomp = comp -- Store the component for later writing
		end
	end
end

-- Example of writing a VariableStorageComponent value
if ( scomp ~= nil ) then
	ComponentSetValue2( scomp, "value_int", status )
end
```