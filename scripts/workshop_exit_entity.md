---
title: Workshop Exit Entity
category: guides
---

<Entity tags="workshop_exit" >
    <CollisionTriggerComponent
      width="52"
      height="52" 
      radius="128"
      destroy_this_entity_when_triggered="1"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/scripts/buildings/workshop_exit.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
</Entity>
```

---
title: Workshop Exit Entity
category: entities
---

# Workshop Exit Entity

This entity represents the exit point of a workshop in Noita. When the player character collides with it, it triggers a specific script.

## Key Components and Attributes

### `CollisionTriggerComponent`

This component defines the area and conditions for triggering an event.

*   **`width`**: `52` - The width of the collision box.
*   **`height`**: `52` - The height of the collision box.
*   **`radius`**: `128` - The radius around the entity that triggers the component.
*   **`destroy_this_entity_when_triggered`**: `1` - The workshop exit entity will be destroyed once triggered.
*   **`required_tag`**: `"player_unit"` - The entity that triggers this component must have the "player\_unit" tag (i.e., the player character).

### `LuaComponent`

This component allows for custom Lua scripting to be executed.

*   **`script_collision_trigger_hit`**: `"data/scripts/buildings/workshop_exit.lua"` - Specifies the Lua script to execute when the `CollisionTriggerComponent` is hit.
*   **`execute_every_n_frame`**: `"-1"` - Indicates that the script should only execute once when triggered, not repeatedly.