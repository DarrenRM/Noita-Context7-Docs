---
title: Dark Moon Altar
category: entities
---

# Dark Moon Altar

This entity represents the Dark Moon Altar, a special building in Noita that interacts with moon energy. It primarily uses Lua scripts to manage its behavior and effects.

## Key Components

### LuaComponent (Main Logic)

This component executes the primary logic for the Dark Moon Altar.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | Set to `1` to enable the component.                                         |
| `execute_every_n_frame` | The script will execute every 90 frames.                                    |
| `script_source_file` | Points to the main Lua script responsible for the altar's functionality.    |

### LuaComponent (Initialization)

This component handles the initial setup and setup-related tasks for the altar.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | Set to `1` to enable the component.                                         |
| `execute_every_n_frame` | The script will execute every 1 frame, indicating immediate or early execution. |
| `script_source_file` | Points to the Lua script for initialization.                                |
| `remove_after_executed` | Set to `1`, meaning this script will be removed after its first execution. |

### LuaComponent (Extra Effects)

This component handles additional or supplementary effects for the altar.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_enabled`          | Set to `1` to enable the component.                                         |
| `execute_every_n_frame` | The script will execute every 80 frames.                                    |
| `script_source_file` | Points to the Lua script for extra effects.                                 |

### LightComponent

This component defines the visual light emitted by the altar.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `_tags`             | Specifies when the light is active (`enabled_in_world`, `enabled_in_hand`). |
| `radius`            | The radius of the light effect (96 pixels).                                 |
| `r`, `g`, `b`       | The color of the light (white: 255, 255, 255).                              |
| `fade_out_time`     | The time it takes for the light to fade out (0.2 seconds).                  |

## Entity Tags

*   `moon_altar`: Identifies this entity as a moon altar.
*   `moon_energy`: Indicates that this entity is related to moon energy.