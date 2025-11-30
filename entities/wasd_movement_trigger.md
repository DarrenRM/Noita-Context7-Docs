---
title: WASD Movement Trigger
category: entities
---

# WASD Movement Trigger

This entity acts as a trigger that activates a Lua script when the player character enters its collision area. It's designed to be used for controlling player movement or triggering events based on proximity.

## Key Components

### CollisionTriggerComponent

This component defines the area that will trigger an event.

| Attribute      | Description                                                                 |
|----------------|-----------------------------------------------------------------------------|
| `width`        | The width of the trigger area.                                              |
| `height`       | The height of the trigger area.                                             |
| `radius`       | The radius of the trigger area (used for circular triggers).                |
| `required_tag` | The tag of the entity that must be present to trigger the event (e.g., `player_unit`). |

### LuaComponent

This component links the trigger event to a specific Lua script.

| Attribute                 | Description                                                                                             |
|---------------------------|---------------------------------------------------------------------------------------------------------|
| `script_collision_trigger_hit` | The path to the Lua script that will be executed when the `CollisionTriggerComponent` is activated. |
| `execute_every_n_frame`   | Controls how often the script is executed. `-1` means it executes only once upon the first hit.        |

## Example Usage

This entity is typically placed in the game world. When the player character (identified by `player_unit` tag) enters the defined collision area, the script specified in `script_collision_trigger_hit` will be executed. The `execute_every_n_frame="-1"` setting ensures the script runs only once when the player first enters the trigger zone.