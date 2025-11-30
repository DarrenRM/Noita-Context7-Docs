---
title: Watchtower Music Trigger
category: biome
---

# Watchtower Music Trigger

This script defines a trigger that plays a specific music track when activated. It's likely used in a "watchtower" biome to introduce a dramatic musical cue.

## Core Functionality

The script's primary function is `collision_trigger()`. This function is designed to be called when an entity interacts with the trigger.

### `collision_trigger()`

This function handles the music playback logic.

*   **`GetUpdatedEntityID()`**: Retrieves the ID of the entity that triggered the event.
*   **`EntityGetTransform( entity_id )`**: Gets the X and Y coordinates of the triggering entity.
*   **`GameTriggerMusicFadeOutAndDequeueAll( 5.0 )`**: Initiates a fade-out of any currently playing music over 5 seconds. This ensures a clean transition to the new track.
*   **`GameTriggerMusicEvent( "music/oneshot/sax_dramatic", true, pos_x, pos_y )`**: Triggers a specific music event.
    *   `"music/oneshot/sax_dramatic"`: The path to the music file to be played. This suggests a dramatic, one-shot saxophone piece.
    *   `true`: Likely indicates that this is a one-shot music event (plays once).
    *   `pos_x`, `pos_y`: The coordinates where the music event is triggered, potentially influencing its spatial audio properties.

## Key Attributes/Elements

*   **Trigger Type**: Implied to be a collision trigger, meaning it activates when an entity physically collides with it.
*   **Music Event**: `"music/oneshot/sax_dramatic"` - The specific music track to play.
*   **Fade Out Duration**: `5.0` seconds for fading out existing music.
*   **Music Playback**: Plays a dramatic, one-shot music cue.
*   **Spatial Audio**: Music is triggered at the entity's position, suggesting potential for positional audio.