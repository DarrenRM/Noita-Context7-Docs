---
title: Smokecave Entry Music Trigger
category: scripts
---

# Smokecave Entry Music Trigger

This script defines a function `collision_trigger` that is intended to be called when an entity enters a specific area, likely the "smokecave". Upon triggering, it plays a music event named "music/smokecave/enter" at the entity's current position.

## Key Functionality

### `collision_trigger()`

This function is the core of the script. It's designed to be executed by the game engine when a collision event occurs.

*   **Purpose:** To initiate a specific music track when an entity enters a designated zone.
*   **Trigger Condition:** Assumed to be a collision event.
*   **Action:** Plays a music event.

### `GameTriggerMusicEvent(event_name, play_once, pos_x, pos_y)`

This is the game API function called by the script.

*   **`event_name`**: `string` - The identifier for the music event to play. In this case, it's `"music/smokecave/enter"`.
*   **`play_once`**: `boolean` - If `true`, the music event will only play once. If `false`, it might loop or be triggered repeatedly. Here, it's set to `true`.
*   **`pos_x`, `pos_y`**: `number` - The X and Y coordinates where the music event should originate. This allows for spatial audio effects.

## Usage Example (Conceptual)

This script would typically be attached to an entity that defines the boundaries of the "smokecave" area. When the player character (or another entity) collides with this boundary entity, the `collision_trigger` function would be invoked.

```lua
-- Example of how this script might be attached to an entity
-- (This is illustrative and not part of the provided script)

-- Assume 'smokecave_boundary_entity' is an entity with a collider
-- and this script is attached to it.

-- When the entity with this script collides with another entity:
-- collision_trigger() is called automatically by the game engine.
```