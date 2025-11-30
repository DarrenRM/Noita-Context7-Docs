---
title: Mountain Enter Music Trigger
category: scripts
---

# Mountain Enter Music Trigger

This script defines a function `collision_trigger` that is intended to be called when a specific entity collides with something. Its primary purpose is to trigger a music event in the game.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. When executed, it performs the following actions:

1.  **Get Updated Entity ID:**
    *   `local entity_id = GetUpdatedEntityID()`
    *   Retrieves the unique identifier of the entity that triggered this function.

2.  **Get Entity Position:**
    *   `local pos_x, pos_y = EntityGetTransform( entity_id )`
    *   Obtains the X and Y coordinates of the entity's current position.

3.  **Trigger Music Event:**
    *   `GameTriggerMusicEvent( "music/mountain/enter", false, pos_x, pos_y )`
    *   This is the main action. It calls the `GameTriggerMusicEvent` function with the following parameters:
        *   `"music/mountain/enter"`: The name of the music event to trigger. This likely corresponds to a specific music track or cue within the game's audio system.
        *   `false`: A boolean flag. In this context, `false` might indicate that the music event should not loop or that it's a one-time trigger.
        *   `pos_x, pos_y`: The X and Y coordinates where the music event should be localized or originate from.

## Usage Context

This script is designed to be attached to an entity within the Noita game engine. When that entity enters a specific area or collides with another object (depending on how `collision_trigger` is invoked by the game), it will play the "music/mountain/enter" track at the entity's location. This is commonly used for environmental cues, such as entering a new biome or triggering a specific atmospheric change.