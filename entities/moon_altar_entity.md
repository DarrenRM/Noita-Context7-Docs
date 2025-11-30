---
title: Moon Altar Entity
category: entities
---

# Moon Altar Entity

This document describes the `moon_altar.xml` entity, which represents a Moon Altar in Noita. This entity is primarily defined by its Lua components, which control its behavior and effects.

## Key Components

### LuaComponent (Main Logic)

This component executes the primary script for the Moon Altar's functionality.

| Attribute           | Value                                   | Description                                                                 |
| :------------------ | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`          | `1`                                     | Enables the component.                                                      |
| `execute_every_n_frame` | `90`                                    | The script will execute every 90 frames.                                    |
| `script_source_file` | `data/scripts/magic/moon_altar.lua`     | Path to the Lua script file that defines the altar's main behavior.         |

### LuaComponent (Initialization)

This component handles the initial setup and setup logic for the Moon Altar.

| Attribute           | Value                                      | Description                                                                 |
| :------------------ | :----------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`          | `1`                                        | Enables the component.                                                      |
| `execute_every_n_frame` | `1`                                        | The script will execute every 1 frame.                                      |
| `script_source_file` | `data/scripts/magic/moon_altar_init.lua`   | Path to the Lua script file for initialization.                             |
| `remove_after_executed` | `1`                                        | This component will be removed after its script has been executed once.     |

### LuaComponent (Extra Logic)

This component executes additional scripts related to the Moon Altar.

| Attribute           | Value                                      | Description                                                                 |
| :------------------ | :----------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`          | `1`                                        | Enables the component.                                                      |
| `execute_every_n_frame` | `80`                                       | The script will execute every 80 frames.                                    |
| `script_source_file` | `data/scripts/magic/moon_altar_extra.lua`  | Path to the Lua script file for extra functionality.                        |

### LightComponent

This component defines the visual light emitted by the Moon Altar.

| Attribute       | Value | Description                                                                 |
| :-------------- | :---- | :-------------------------------------------------------------------------- |
| `_tags`         | `enabled_in_world,enabled_in_hand` | The light is active when the entity is in the world or held in hand.        |
| `radius`        | `96`  | The radius of the light effect.                                             |
| `r`, `g`, `b`   | `255` | Sets the light color to white (RGB values).                                 |
| `fade_out_time` | `0.2` | The time it takes for the light to fade out.                                |