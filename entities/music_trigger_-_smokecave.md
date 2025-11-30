---
title: Music Trigger - Smokecave
category: entities
---

# Music Trigger - Smokecave

This entity acts as a trigger to play specific audio when the player enters a designated area, likely within the Smokecave biome.

## Key Components

### CollisionTriggerComponent

This component defines the area that, when entered by an entity with the `player_unit` tag, will activate the associated Lua script.

*   **`width`**: `110` - The width of the trigger area.
*   **`height`**: `300` - The height of the trigger area.
*   **`radius`**: `160` - The radius of the trigger area.
*   **`required_tag`**: `player_unit` - Only entities tagged as `player_unit` will trigger this component.

### LuaComponent

This component links the collision trigger to a specific Lua script that handles the audio playback.

*   **`script_collision_trigger_hit`**: `data/scripts/audio/smokecave_enter.lua` - The path to the Lua script executed when the collision trigger is hit.
*   **`execute_every_n_frame`**: `-1` - Indicates the script should execute only once upon trigger activation.