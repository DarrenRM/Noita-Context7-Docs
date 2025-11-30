---
title: Mountain Left Entrance Music Trigger
category: entities
---

# Mountain Left Entrance Music Trigger

This entity defines a trigger that plays music when the player enters a specific area, likely the left entrance to the mountain biome.

## Key Components

### CollisionTriggerComponent

This component detects when an entity with the `player_unit` tag enters its defined collision area.

*   **`width`**: `110` - The width of the trigger area.
*   **`height`**: `160` - The height of the trigger area.
*   **`radius`**: `200` - The radius of the trigger area.
*   **`required_tag`**: `player_unit` - Only entities tagged as `player_unit` will activate this trigger.

### LuaComponent

This component executes a Lua script when the `CollisionTriggerComponent` is activated.

*   **`script_collision_trigger_hit`**: `data/scripts/audio/mountain_enter.lua` - The path to the Lua script that will be executed upon collision. This script is responsible for playing the music.
*   **`execute_every_n_frame`**: `-1` - This indicates the script will execute only once when the trigger is hit.

```xml
<Entity>
    <CollisionTriggerComponent
      width="110"
      height="160"
      radius="200"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/scripts/audio/mountain_enter.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
</Entity>
```