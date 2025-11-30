---
title: Boss Music Buildup Trigger
category: entities
---

# Boss Music Buildup Trigger

This entity acts as a trigger to initiate the boss arena music buildup sequence. When an entity collides with this trigger, it sets a global variable and plays a specific music event.

## Key Functionality

### `collision_trigger()`

This function is called when a collision occurs with the entity.

*   **Purpose:** To activate the boss music buildup.
*   **Actions:**
    *   Retrieves the ID and position of the triggering entity.
    *   Prints a debug message to the console.
    *   Sets the global variable `BOSS_ARENA_BUILDUP_TRIGGERED` to "1".
    *   Triggers the music event `"music/boss_arena/buildup"` at the entity's position.

## Lua Code

```lua
dofile( "data/scripts/lib/utilities.lua" )

function collision_trigger()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )
	
	print("Boss buildup music triggered")

	GlobalsSetValue( "BOSS_ARENA_BUILDUP_TRIGGERED", "1" )
	GameTriggerMusicEvent( "music/boss_arena/buildup", true,  pos_x, pos_y )
end
```