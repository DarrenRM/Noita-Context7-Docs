---
title: Low Gravity Perk
category: scripts/perks
---

# Low Gravity Perk

This script implements the "Low Gravity" perk in Noita. When a player picks up this perk, it applies a reduced gravity effect to entities that have the "homing_target" tag. This effect is applied by modifying the `pixel_gravity` of `CharacterPlatformingComponent` and the `gravity` of `WormComponent`.

## Key Functionality

*   **Targeting:** The script identifies entities with the "homing_target" tag.
*   **Gravity Reduction:** For each identified target, it reduces its gravity by 60% (multiplies by 0.4).
*   **Component Modification:**
    *   Modifies `CharacterPlatformingComponent`'s `pixel_gravity`.
    *   Modifies `WormComponent`'s `gravity`.
*   **Tagging:** Applies the "low_gravity" tag to entities that have had their gravity modified to prevent repeated application.

## Code Structure

The script uses `dofile_once` to ensure utility functions are loaded. It then retrieves the current entity ID and searches for entities with the "homing_target" tag. A loop iterates through these targets, checks if they already have the "low_gravity" tag, and if not, proceeds to modify their gravity components and add the tag.

### Core Logic Snippet

```lua
local entity_id = GetUpdatedEntityID()

local targets = EntityGetWithTag( "homing_target" )

if ( #targets > 0 ) then
	for i,target_id in ipairs( targets ) do
		if ( EntityHasTag( target_id, "low_gravity" ) == false ) then
			-- Gravity modification logic here
			EntityAddTag( target_id, "low_gravity" )
		end
	end
end
```

## Components Affected

### CharacterPlatformingComponent

This component handles the platforming physics for characters. The `pixel_gravity` attribute is directly modified.

*   **`pixel_gravity`**: The value is multiplied by `0.4`, reducing gravity by 60%.

### WormComponent

This component is likely used for worm-like entities. The `gravity` attribute is modified.

*   **`gravity`**: The value is multiplied by `0.4`, reducing gravity by 60%.

## AI Modding Considerations

When AI modding this perk, consider:

*   **Target Selection:** How can you influence which entities receive the "homing\_target" tag?
*   **Gravity Values:** Experiment with different multipliers for `pixel_gravity` and `gravity` to create unique gameplay effects.
*   **Perk Acquisition:** How will the player acquire this perk? This script only handles the *effect* of the perk.
*   **Entity Types:** Which entities are most affected by low gravity? Consider how this might interact with other AI behaviors.