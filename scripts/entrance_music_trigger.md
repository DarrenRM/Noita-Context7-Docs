---
title: Entrance Music Trigger
category: scripts
---

# Entrance Music Trigger

This script defines a function `collision_trigger` that is intended to be called when an entity collides with something. Its primary purpose is to trigger a specific music event in the game.

## Function: `collision_trigger`

This function is designed to be attached to an entity that will initiate a music change upon interaction or collision.

### Key Actions:

*   **Get Updated Entity ID:** Retrieves the unique identifier for the entity that triggered the event.
*   **Get Entity Position:** Obtains the current X and Y coordinates of the entity.
*   **Trigger Music Event:** Calls the `GameTriggerMusicEvent` function to play a specific music track.

### Parameters for `GameTriggerMusicEvent`:

*   **`"music/entrance/enter"`:** The identifier for the music event to be triggered. This likely corresponds to a music track named "enter" within the "music/entrance" directory.
*   **`true`:** A boolean flag, likely indicating that this music event should start playing.
*   **`pos_x`:** The X-coordinate of the entity, used to position the music event in the game world.
*   **`pos_y`:** The Y-coordinate of the entity, used to position the music event in the game world.

### Usage Example (Conceptual):

This script would typically be attached to an entity that represents an entrance or a transition point in the game. When the player's character collides with this entity, the `collision_trigger` function would execute, causing the "entrance/enter" music to begin playing.

```lua
-- Example of how this script might be used in an entity definition:
--
-- local entity_id = EntityLoad( "data/entities/your_entrance_entity.xml" )
-- EntityAddChildGetID( entity_id, "data/scripts/audio/entrance_enter.lua" )
-- EntitySetCallback( entity_id, "ON_COLLISION", "collision_trigger" )
```