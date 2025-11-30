---
title: Orb 07 Pitcheck A
category: entities
---

# Orb 07 Pitcheck A

This entity acts as a trigger that detects when the player enters a specific area, likely to initiate an event or check for a condition.

## Key Components

### CollisionTriggerComponent

This component defines the collision area and the conditions for triggering an event.

| Attribute                 | Value | Description                                                                 |
| :------------------------ | :---- | :-------------------------------------------------------------------------- |
| `width`                   | 96    | The width of the rectangular collision area.                                |
| `height`                  | 110   | The height of the rectangular collision area.                               |
| `radius`                  | 60    | The radius of the circular collision area (used in conjunction with width/height). |
| `destroy_this_entity_when_triggered` | 1     | When triggered, this entity will be destroyed.                              |
| `required_tag`            | `player_unit` | The entity must have the tag "player_unit" to trigger this component.       |

### LuaComponent

This component executes a Lua script when the `CollisionTriggerComponent` is activated.

| Attribute                 | Value                                           | Description                                                                                             |
| :------------------------ | :---------------------------------------------- | :------------------------------------------------------------------------------------------------------ |
| `script_collision_trigger_hit` | `data/scripts/buildings/orb_07_pitcheck_a.lua` | The path to the Lua script that will be executed when the collision trigger is hit by a required tag. |
| `execute_every_n_frame`   | -1                                              | This script will execute only once when triggered, as -1 typically signifies a single execution.        |