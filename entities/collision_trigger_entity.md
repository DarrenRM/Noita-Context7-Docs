---
title: Collision Trigger Entity
category: entities
---

# Collision Trigger Entity

This entity defines a trigger that activates when a specified entity (typically the player) enters its collision area. It's commonly used for triggering events or scripts when the player interacts with a specific part of the environment.

## Key Components

### CollisionTriggerComponent

This component defines the physical area and conditions for the trigger.

| Attribute       | Description                                                                 |
| --------------- | --------------------------------------------------------------------------- |
| `width`         | The width of the rectangular collision area.                                |
| `height`        | The height of the rectangular collision area.                               |
| `radius`        | The radius of the circular collision area (if applicable, often used in conjunction with width/height). |
| `required_tag`  | The entity tag that must be present on an colliding entity for the trigger to activate (e.g., `player_unit`). |

### LuaComponent

This component links the collision trigger to a Lua script that will be executed when the trigger is activated.

| Attribute                 | Description                                                                                             |
| ------------------------- | ------------------------------------------------------------------------------------------------------- |
| `script_collision_trigger_hit` | The path to the Lua script file that will be executed when the `CollisionTriggerComponent` is hit. |
| `execute_every_n_frame`   | Determines how often the script is executed. `-1` typically means execute only once upon initial hit. |

## Example Usage

This entity is often placed in the game world to detect player proximity and initiate specific actions, such as opening doors, activating mechanisms, or starting cutscenes.

```xml
<Entity>
    <CollisionTriggerComponent
      width="16"
      height="96"
      radius="128"
      required_tag="player_unit" >
  	</CollisionTriggerComponent>

    <LuaComponent
      script_collision_trigger_hit="data/scripts/buildings/controls_f_trigger.lua"
      execute_every_n_frame="-1" >
    </LuaComponent>
</Entity>
```