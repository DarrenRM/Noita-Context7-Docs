---
title: Lava Lake Music Trigger
category: entities
---

# Lava Lake Music Trigger

This entity defines a trigger that plays a specific sound when the player enters a designated area, simulating the atmosphere of a lava lake.

## Key Components

### CollisionTriggerComponent

This component defines the area that, when entered by an entity with the `player_unit` tag, will activate the associated Lua script.

*   **`width`**: `110` - The width of the trigger area.
*   **`height`**: `300` - The height of the trigger area.
*   **`radius`**: `160` - The radius of the trigger area (likely used in conjunction with width/height for a more complex shape or as a fallback).
*   **`required_tag`**: `player_unit` - Specifies that the trigger only activates when the player character enters the area.

### LuaComponent

This component links the collision trigger to a specific Lua script that will be executed upon activation.

*   **`script_collision_trigger_hit`**: `data/scripts/audio/lavalake_enter.lua` - The path to the Lua script that will be executed when the `CollisionTriggerComponent` is hit by an entity with the `player_unit` tag. This script is responsible for playing the lava lake sound effect.
*   **`execute_every_n_frame`**: `-1` - Indicates that the script should execute only once when the trigger is hit, not repeatedly.