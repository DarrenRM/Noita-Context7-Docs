---
title: Hourglass Music Trigger Script
category: guides
---

function collision_trigger()
	local entity_id = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform(entity_id)
	
	print("play jingle")
	GameTriggerMusicFadeOutAndDequeueAll( 3.0 )
	GameTriggerMusicEvent( "music/oneshot/ei_vihuja_01", true, pos_x, pos_y )
end
```
---
title: Hourglass Music Trigger Script
category: scripts
---

# Hourglass Music Trigger Script

This script defines a simple trigger that plays a specific music track when an entity collides with it. It's designed to be attached to an entity that acts as a trigger volume.

## Key Functionality

### `collision_trigger()`

This function is executed when a collision event occurs for the entity this script is attached to.

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered the event.
*   **`EntityGetTransform(entity_id)`**: Gets the position (x, y) of the triggering entity.
*   **`print("play jingle")`**: Logs a message to the console, indicating the music trigger is activated.
*   **`GameTriggerMusicFadeOutAndDequeueAll( 3.0 )`**: Initiates a fade-out of all currently playing music tracks over 3.0 seconds.
*   **`GameTriggerMusicEvent( "music/oneshot/ei_vihuja_01", true, pos_x, pos_y )`**: Triggers a specific music event.
    *   `"music/oneshot/ei_vihuja_01"`: The path to the music file to be played.
    *   `true`: Indicates this is a one-shot music event.
    *   `pos_x`, `pos_y`: The position where the music event originates.

## Usage

Attach this script to an entity that should act as a music trigger. When another entity (e.g., the player) collides with this trigger entity, the specified music will play after a short fade-out.