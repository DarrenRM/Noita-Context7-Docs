---
title: Temple Left Music Trigger
category: entities
---

# Temple Left Music Trigger

This entity defines a trigger that plays a specific sound when the player enters a designated area.

## Key Components

### CollisionTriggerComponent

This component defines the area and conditions for triggering an event.

| Attribute      | Value   | Description                                     |
|----------------|---------|-------------------------------------------------|
| `width`        | `110`   | The width of the trigger area.                  |
| `height`       | `110`   | The height of the trigger area.                 |
| `radius`       | `160`   | The radius of the trigger area (likely circular). |
| `required_tag` | `player_unit` | The entity must have this tag to trigger the event. |

### LuaComponent

This component executes a Lua script when the trigger is activated.

| Attribute                 | Value                                  | Description                                                              |
|---------------------------|----------------------------------------|--------------------------------------------------------------------------|
| `script_collision_trigger_hit` | `data/scripts/audio/temple_enter.lua` | The path to the Lua script to execute when the trigger is hit.           |
| `execute_every_n_frame`   | `-1`                                   | This value indicates the script should execute only once per trigger hit. |