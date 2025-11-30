---
title: Longleg Pet Interaction Script
category: scripts
---

# Longleg Pet Interaction Script

This script defines the behavior when a player interacts with a "longleg" creature, aiming to "pet" it. The interaction can result in the creature becoming friendly or, rarely, exploding.

## Core Functionality: `interacting`

This function is triggered when an entity interacts with the longleg.

### Key Actions:

1.  **Stop Movement:** Both the interacting entity and the longleg have their velocities reset to zero. This ensures a stable interaction.
2.  **Random Outcome:** A random number is generated to determine the interaction's success.
3.  **Success (Petting):**
    *   The longleg plays a "pet" animation.
    *   Components tagged "enabled\_if\_charmed" are disabled on the longleg.
    *   A positive message (`$ui_longleg_love_msg1`) is displayed to the player.
4.  **Failure (Explosion):**
    *   An explosion projectile is spawned at the longleg's location.
    *   A negative message (`$ui_longleg_love_msg2`) is displayed to the player.
5.  **Sound Effect:** A "pet" sound is played for the interacting entity.

### Code Snippet:

```lua
function interacting(entity_who_interacted, entity_interacted, interactable_name)
	local x, y = EntityGetTransform( entity_interacted )

	-- Stop movement for both entities
	edit_component( entity_interacted, "VelocityComponent", function(comp,vars)
		ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
	end)
	edit_component( entity_interacted, "CharacterDataComponent", function(comp,vars)
		ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
	end)
	edit_component( entity_who_interacted, "VelocityComponent", function(comp,vars)
		ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
	end)
	edit_component( entity_who_interacted, "CharacterDataComponent", function(comp,vars)
		ComponentSetValueVector2( comp, "mVelocity", 0, 0 )
	end)

	-- Determine random outcome
	SetRandomSeed( x + entity_interacted, y + GameGetFrameNum() )
	local rnd = Random( 1, 20 )

	if ( rnd ~= 13 ) then
		-- Success: Petting
		GamePlayAnimation( entity_interacted, "pet", 99, "stand", 0 )
		EntitySetComponentsWithTagEnabled( entity_interacted, "enabled_if_charmed", false )
		GamePrint( "$ui_longleg_love_msg1" )
	else
		-- Failure: Explosion
		EntityLoad( "data/entities/projectiles/explosion.xml", x, y )
		GamePrint( "$ui_longleg_love_msg2" )
	end

	-- Play interaction sound
	GameEntityPlaySound( entity_who_interacted, "pet" )
end
```