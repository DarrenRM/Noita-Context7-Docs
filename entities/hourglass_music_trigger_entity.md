---
title: Hourglass Music Trigger Entity
category: entities
---

# Hourglass Music Trigger Entity

This entity defines a trigger that plays music when the player enters its area. It's designed to be a one-time event.

## Key Components

### LuaComponent

This component links the entity to a Lua script that handles the logic for the trigger.

*   **`script_collision_trigger_hit`**: Specifies the Lua script to execute when the collision trigger is activated.
    *   Value: `data/scripts/buildings/hourglass_music_trigger.lua`
*   **`execute_times`**: Determines how many times the script can be executed.
    *   Value: `1` (meaning it will only trigger once)

### CollisionTriggerComponent

This component defines the area and conditions for triggering the Lua script.

*   **`width`**: The width of the rectangular trigger area.
    *   Value: `360`
*   **`height`**: The height of the rectangular trigger area.
    *   Value: `180`
*   **`radius`**: The radius of a circular area, likely used in conjunction with or as an alternative to the rectangular dimensions for trigger detection.
    *   Value: `200`
*   **`required_tag`**: The tag of the entity that must be present to activate the trigger.
    *   Value: `player_unit` (meaning the player character)
*   **`destroy_this_entity_when_triggered`**: A flag to determine if the entity should be destroyed after triggering.
    *   Value: `1` (true, the entity will be destroyed after triggering)

```xml
<Entity tags="hourglass_entity">
	<LuaComponent
		script_collision_trigger_hit="data/scripts/buildings/hourglass_music_trigger.lua"
		execute_times="1" >
	</LuaComponent>

	<CollisionTriggerComponent
		width="360"
		height="180"
		radius="200"
		required_tag="player_unit"
		destroy_this_entity_when_triggered="1" >
	</CollisionTriggerComponent>
</Entity>
```