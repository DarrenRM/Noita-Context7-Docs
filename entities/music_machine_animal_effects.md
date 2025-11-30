---
title: Music Machine Animal Effects
category: entities
---

# Music Machine Animal Effects

This script defines the behavior of a music machine that interacts with nearby "helpless_animal" entities. When activated, it has a chance to apply visual effects (question mark or charm) and play a sound to confused animals.

## Key Functionality

*   **Entity Identification:** The script identifies the music machine entity and its position.
*   **Animal Detection:** It searches for entities with the tag "helpless_animal" within a 700-unit radius.
*   **AI Check:** It filters out animals that already have an `AdvancedFishAIComponent`, implying they are not "helpless" in the intended way.
*   **Randomized Effects:** For eligible animals, there's a 30% chance to trigger an effect.
    *   Within that 30%, there's a 50% chance to spawn a `questionmark_oneoff.xml` particle effect.
    *   Otherwise, a `charm_oneoff.xml` particle effect is spawned.
*   **Sound Playback:** If an effect is triggered, there's a 50% chance to play the "confused" sound on the animal.

## Core Logic Breakdown

```lua
-- Ensure fx are not left running in case game was closed while the machine was active
local entity = GetUpdatedEntityID()
local x,y = EntityGetTransform( entity )

-- Find helpless animals within a radius
local animals = EntityGetInRadiusWithTag( x, y, 700, "helpless_animal" )

-- Iterate through detected animals
for i,animal in ipairs(animals) do
	-- Check if the animal has a specific AI component, skip if it does
	if EntityGetFirstComponent( animal, "AdvancedFishAIComponent" ) == nil then
		local px,py = EntityGetTransform( animal )
		SetRandomSeed( px, py ) -- Seed random number generator based on animal position

		-- 30% chance to apply effects
		if Random( 1, 100 ) <= 30 then
			-- 50% chance for question mark effect, 50% for charm effect
			if Random( 1, 100 ) <= 50 then
				EntityLoad( "data/entities/particles/questionmark_oneoff.xml", px, py-16 )
			else
				EntityLoad( "data/entities/particles/charm_oneoff.xml", px, py-16 )
			end

			-- 50% chance to play a sound
			if Random( 1, 100 ) <= 50 then
				GameEntityPlaySound( animal, "confused" )
			end
		end
	end
end
```