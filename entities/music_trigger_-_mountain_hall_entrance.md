---
title: Music Trigger - Mountain Hall Entrance
category: entities
---

# Music Trigger - Mountain Hall Entrance

This entity defines a trigger that plays a specific sound when the player enters a designated area.

## Key Components

### CollisionTriggerComponent

This component defines the area that, when entered by an entity with the `player_unit` tag, will activate the associated Lua script.

*   **`width`**: 50 (Width of the trigger area)
*   **`height`**: 240 (Height of the trigger area)
*   **`radius`**: 200 (Radius of the trigger area, likely for circular detection)
*   **`required_tag`**: `player_unit` (Only the player can trigger this)

### LuaComponent

This component links the collision trigger to a specific Lua script that will be executed upon activation.

*   **`script_collision_trigger_hit`**: `data/scripts/audio/entrance_enter.lua` (The script to execute when the trigger is hit)
*   **`execute_every_n_frame`**: -1 (Indicates the script should execute only once per trigger activation)

```xml
<Entity>
    <CollisionTriggerComponent
      width="50"
      height="240" 
      radius="200"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/scripts/audio/entrance_enter.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
</Entity>
```