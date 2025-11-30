---
title: Temple Music Trigger
category: entities
---

# Temple Music Trigger

This entity defines a trigger that plays music when the player enters a specific area, likely within a temple environment.

## Key Components

### CollisionTriggerComponent

This component defines the area that will trigger an event when the player enters it.

| Attribute     | Value   | Description                                                                 |
|---------------|---------|-----------------------------------------------------------------------------|
| `width`       | `50`    | The width of the rectangular trigger area.                                  |
| `height`      | `240`   | The height of the rectangular trigger area.                                 |
| `radius`      | `200`   | The radius of the circular trigger area (used in conjunction with width/height). |
| `required_tag`| `player_unit` | The entity tag that must be present to activate the trigger (the player). |

### LuaComponent

This component executes a Lua script when the `CollisionTriggerComponent` is activated.

| Attribute                   | Value                                       | Description                                                                                             |
|-----------------------------|---------------------------------------------|---------------------------------------------------------------------------------------------------------|
| `script_collision_trigger_hit` | `data/scripts/audio/temple_enter.lua`       | The path to the Lua script to execute when the trigger is hit. This script likely handles the music playback. |
| `execute_every_n_frame`     | `-1`                                        | This value indicates the script should execute only once when the trigger is hit, not repeatedly.       |