---
title: Inventory Trigger Building
category: entities
---

# Inventory Trigger Building

This entity defines a building that triggers an action when the player enters its collision area. It's commonly used for inventory-related events.

## Key Components

### CollisionTriggerComponent

This component defines the physical area that triggers an event.

| Attribute     | Description                                                              |
|---------------|--------------------------------------------------------------------------|
| `width`       | The width of the trigger area.                                           |
| `height`      | The height of the trigger area.                                          |
| `radius`      | The radius of the trigger area (if circular).                            |
| `required_tag`| The tag of the entity that must enter the trigger area to activate it.   |

### LuaComponent

This component links the collision trigger to a Lua script that handles the event logic.

| Attribute                 | Description                                                                                             |
|---------------------------|---------------------------------------------------------------------------------------------------------|
| `script_collision_trigger_hit` | The path to the Lua script that will be executed when the `CollisionTriggerComponent` is activated. |
| `execute_every_n_frame`   | Controls how often the script is executed. `-1` typically means execute once on trigger.                |

## Example Usage

When a player (with the `player_unit` tag) enters the defined collision area of this building, the script specified in `script_collision_trigger_hit` will be executed. This script would then handle the specific inventory-related logic, such as opening an inventory menu or triggering a specific item interaction.