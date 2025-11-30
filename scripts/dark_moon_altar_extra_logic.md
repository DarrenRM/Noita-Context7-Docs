---
title: Dark Moon Altar Extra Logic
category: scripts
---

# Dark Moon Altar Extra Logic

This script defines the logic for a special altar in Noita, likely related to a "Dark Moon" event. It checks for specific game conditions and player actions to trigger a unique effect.

## Key Functionality

The primary function of this script is to activate a special event when a set of prerequisites are met. These prerequisites involve the player possessing all four elemental essences and interacting with a specific entity tagged with `u_dheglmticg`.

### Prerequisites for Activation

*   **Essence Collection:** The player must have collected all four elemental essences:
    *   `essence_fire`
    *   `essence_air`
    *   `essence_water`
    *   `essence_laser`
*   **Altar Interaction:** The player must be near an entity tagged with `u_dheglmticg`. This likely represents the "Dark Moon Altar" itself.

### Triggered Effects

Upon successful activation, the script performs the following actions:

1.  **Persistent Flag:** Sets a persistent game flag named `aejafxooa`. This flag likely signifies that the Dark Moon event has been initiated or completed.
2.  **Visual Effect:** Spawns a specific entity (`data/entities/misc/moon_effect_test2.xml`) at the altar's location, creating a visual representation of the event.
3.  **HP Heart Spawns:** Spawns ten "full HP heart" entities (`data/entities/misc/magic/heart_fullhp.xml`) in a horizontal line near the altar. This suggests a potential reward or healing effect for the player.
4.  **In-Game Message:** Displays an important message to the player using the keys `$log_dark_moon_altar_extra` and `$logdesc_dark_moon_altar_extra`. These are likely localization keys for the message text.
5.  **Altar Destruction:** The altar entity itself is destroyed (`EntityKill(entity_id)`), preventing further interactions.

## Code Breakdown

```lua
-- Ensures this script runs only once.
dofile_once("data/scripts/lib/utilities.lua")

-- Gets the unique ID of the current entity (the altar).
local entity_id = GetUpdatedEntityID()
-- Gets the world coordinates (x, y) of the altar.
local x, y = EntityGetTransform( entity_id )

-- Retrieves the internal name for the flag associated with the altar.
local test = get_flag_name( "u_dheglmticg" )
-- Retrieves the internal name for the flag that will be set upon activation.
local test2 = get_flag_name( "aejafxooa" )

-- Checks if the player possesses each of the four elemental essences.
local essence_1 = GameHasFlagRun( "essence_fire" )
local essence_2 = GameHasFlagRun( "essence_air" )
local essence_3 = GameHasFlagRun( "essence_water" )
local essence_4 = GameHasFlagRun( "essence_laser" )

-- Finds entities tagged with the altar's identifier.
local targets = EntityGetWithTag( test )
-- Finds any player units within a 48-unit radius of the altar.
local targets2 = EntityGetInRadiusWithTag( x, y, 48, "player_unit" )

-- Conditional check for all prerequisites.
if essence_1 and essence_2 and essence_3 and essence_4 and ( #targets > 0 ) and ( #targets2 > 0 ) then
	-- Sets the persistent flag indicating activation.
	AddFlagPersistent( test2 )
	
	-- Loads the visual effect entity at the altar's position.
	EntityLoad("data/entities/misc/moon_effect_test2.xml", x, y)
	
	-- Spawns 10 HP hearts in a line.
	for i=1,10 do
		EntityLoad("data/entities/misc/magic/heart_fullhp.xml", x - 100 + (i-1) * 20, y - 64)
	end
	
	-- Displays the important in-game message.
	GamePrintImportant( "$log_dark_moon_altar_extra", "$logdesc_dark_moon_altar_extra" )
	
	-- Destroys the altar entity.
	EntityKill( entity_id )
end
```