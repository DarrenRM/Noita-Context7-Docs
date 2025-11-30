---
title: Workshop Trigger Check Stats
category: entities
---

# Workshop Trigger Check Stats

This entity defines a trigger that activates when the player unit collides with it. It's designed to initiate a Lua script for checking player statistics within a workshop context.

## Key Components

### CollisionTriggerComponent

This component handles the collision detection and the conditions for triggering.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `width`                   | The width of the collision box.                                             |
| `height`                  | The height of the collision box.                                            |
| `radius`                  | The radius of the collision detection.                                      |
| `destroy_this_entity_when_triggered` | If set to `1`, the entity will be destroyed once the trigger condition is met. |
| `required_tag`            | The tag of the entity that must collide to trigger the event (e.g., `player_unit`). |

### LuaComponent

This component links the trigger event to a specific Lua script.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `script_collision_trigger_hit` | The path to the Lua script to execute when the `CollisionTriggerComponent` is hit. |
| `execute_every_n_frame`   | Controls how often the script is executed. `-1` means it executes only once. |

## Usage

When an entity with the tag `player_unit` collides with this trigger, the specified Lua script (`data/scripts/buildings/workshop_trigger_check_stats.lua`) will be executed. The trigger entity itself will be destroyed upon activation. This setup is commonly used for events that should occur once when the player interacts with a specific workshop element.