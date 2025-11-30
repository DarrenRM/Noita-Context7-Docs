---
title: Music Machine 01 Entity
category: entities
---

# Music Machine 01 Entity

This document describes the `music_machine_01.lua` entity, a functional music machine prop in Noita.

## Entity Definition

The entity is defined by the `kick` function, which is triggered when the machine is interacted with.

### Key Functionality: `kick`

The `kick` function handles the logic for activating the music machine.

*   **Sound Playback:** Plays the sound "01" associated with the machine.
*   **Visual Effects:** Enables components tagged with "fx" to trigger visual effects.
*   **Attraction:** Adds the "fish_attractor" tag to the entity, potentially influencing nearby fish.
*   **Global Flag:** Sets a global game flag named "musicmachine2".

### Lua Script

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

function kick( who_kicked )
	local entity = GetUpdatedEntityID()

	local src = -1
	edit_component( entity, "AudioComponent", function(comp,vars)
		src = ComponentGetValue2( comp, "m_latest_source" )
	end)

	if src == -1 then
		GameEntityPlaySound( entity, "01" )
		EntitySetComponentsWithTagEnabled( entity, "fx", true )
		EntityAddTag( entity, "fish_attractor" )
		
		GameAddFlagRun( "musicmachine2" )
	end
end
```