---
title: Necromancer Shop Death Logic
category: scripts
---

# Necromancer Shop Death Logic

This script defines the behavior when a "Necromancer Shop" entity dies. It tracks the number of deaths and triggers specific events after a certain threshold.

## Key Attributes

*   **Death Counter:** Increments a global variable `STEVARI_DEATHS` each time the entity dies.
*   **Death Threshold:** If `STEVARI_DEATHS` reaches 3 or more, special events are triggered.

## Triggered Events (at 3+ deaths)

*   **Important Message:** Displays the message "$logdesc_temple_upgrade_guardian" to the player.
*   **Sound Effect:** Plays the sound "event_cues/angered_the_gods/create".
*   **Screen Shake:** Initiates a screen shake with an intensity of 50.

## Lua Code

```lua
function death()
	local entity_id = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform(entity_id)

	-- Increment the global death counter
	local deaths = tonumber(GlobalsGetValue("STEVARI_DEATHS", "0"))
	deaths = deaths + 1
	GlobalsSetValue("STEVARI_DEATHS", tostring(deaths))

	-- Check if the death threshold has been met
	if deaths >= 3 then
		-- Display an important message to the player
		GamePrintImportant( "$logdesc_temple_upgrade_guardian", "" )
		-- Play a specific sound effect at the entity's position
		GamePlaySound( "data/audio/Desktop/event_cues.bank", "event_cues/angered_the_gods/create", pos_x, pos_y )
		-- Trigger a screen shake
		GameScreenshake( 50 )
	end
end
```