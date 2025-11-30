---
title: Dragon Spot Entity
category: entities
---

# Dragon Spot Entity

This entity represents a "Dragon Spot" within the game world. It's primarily used to trigger specific events or behaviors when the player character comes into proximity.

## Key Components

### CollisionTriggerComponent

This component defines the area and conditions for triggering an event.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `width`                   | The width of the collision trigger area.                                    |
| `height`                  | The height of the collision trigger area.                                   |
| `radius`                  | The radius of the circular collision trigger area.                          |
| `required_tag`            | The tag of the entity that must trigger the collision (e.g., `player_unit`). |
| `destroy_this_entity_when_triggered` | Whether the entity should be destroyed after being triggered (0 for no). |

### LuaComponent

This component links the collision trigger to a specific Lua script for custom logic.

| Attribute                 | Description                                                                 |
| :------------------------ | :-------------------------------------------------------------------------- |
| `script_collision_trigger_hit` | The path to the Lua script to execute when the collision is triggered.      |
| `execute_every_n_frame`   | How often the script should execute (-1 means only once on trigger).        |

## Example Usage

The `dragonspot.xml` file defines an entity that, when the player unit enters its collision radius, will execute the script located at `data/scripts/buildings/dragonspot.lua`. The entity itself is not destroyed upon triggering.