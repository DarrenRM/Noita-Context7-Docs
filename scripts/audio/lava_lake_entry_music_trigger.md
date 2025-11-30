---
title: Lava Lake Entry Music Trigger
category: scripts/audio
---

# Lava Lake Entry Music Trigger

This script defines a function that triggers a specific music event when a collision occurs. It's designed to play the "enter" music for the lava lake biome.

## Functionality

The `collision_trigger` function is the core of this script. When called, it performs the following actions:

### Key Actions

1.  **Get Entity ID:** Retrieves the unique identifier of the entity that triggered the collision.
2.  **Get Entity Position:** Obtains the X and Y coordinates of the entity's transform.
3.  **Trigger Music Event:** Calls `GameTriggerMusicEvent` to play the designated music.

## Lua Code

```lua
function collision_trigger()
	local entity_id    = GetUpdatedEntityID()
	local pos_x, pos_y = EntityGetTransform( entity_id )

	GameTriggerMusicEvent( "music/lavalake/enter", true, pos_x, pos_y )
end
```

## Parameters for `GameTriggerMusicEvent`

*   **`"music/lavalake/enter"`**: The path to the music file to be played. This specifically targets the lava lake entry music.
*   **`true`**: A boolean flag, likely indicating whether the music should loop or play once. In this context, it's probable that `true` signifies playing the music upon entry.
*   **`pos_x`**: The X-coordinate of the entity triggering the event. This allows for spatial audio positioning.
*   **`pos_y`**: The Y-coordinate of the entity triggering the event. This allows for spatial audio positioning.