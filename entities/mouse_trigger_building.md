---
title: Mouse Trigger Building
category: entities
---

# Mouse Trigger Building

This entity acts as a trigger that activates when the player's mouse cursor enters its collision area. It's commonly used for simple on-hover interactions.

## Key Components

### CollisionTriggerComponent

This component defines the physical area that the mouse cursor needs to enter to trigger an event.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `width`       | The width of the trigger area.                                           |
| `height`      | The height of the trigger area.                                          |
| `radius`      | The radius of the trigger area (if circular).                            |
| `required_tag`| The entity tag that must be present for the trigger to activate (e.g., `player_unit`). |

### LuaComponent

This component links the trigger event to a specific Lua script that will be executed.

| Attribute                 | Description                                                              |
|---------------------------|--------------------------------------------------------------------------|
| `script_collision_trigger_hit` | The path to the Lua script to execute when the trigger is hit.           |
| `execute_every_n_frame`   | How often the script should execute. `-1` means execute once on hit.      |

## Example Usage

This building is typically placed in the game world and configured with a `CollisionTriggerComponent` and a `LuaComponent` pointing to a script that handles the desired mouse-over effect.