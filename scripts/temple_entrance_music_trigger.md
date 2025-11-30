---
title: Temple Entrance Music Trigger
category: scripts
---

---

# Temple Entrance Music Trigger

This script defines the behavior for triggering music when a player enters the temple area in Noita.

## Function: `collision_trigger()`

This function is called when the entity associated with this script collides with something, typically the player.

### Key Actions:

1.  **Get Entity ID and Position:**
    *   `local entity_id = GetUpdatedEntityID()`: Retrieves the ID of the entity that triggered the event.
    *   `local pos_x, pos_y = EntityGetTransform( entity_id )`: Gets the world coordinates of the entity.

2.  **Music Event Triggering (Commented Out Logic):**
    *   The original logic for triggering specific music based on a global flag (`TEMPLE_SPAWN_GUARDIAN`) is commented out.
    *   The current implementation relies on `game_music.cpp` to handle music events based on internal game states.

3.  **Setting Active Flag:**
    *   `temple_set_active_flag( pos_x, pos_y, "1" )`: This is the primary action. It sets an internal flag related to the temple being active at the given position. This flag likely influences game logic and music playback handled by the game's core systems.

## Dependencies

*   `dofile_once("data/scripts/biomes/temple_shared.lua")`: This line ensures that shared functions and definitions for temple biomes are loaded and available.

## Notes

*   The direct music triggering logic within this script has been superseded by game engine functionality, indicated by the commented-out code.
*   The main purpose of this script is to signal to the game that the player has entered the temple area by setting an appropriate flag.