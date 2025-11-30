---
title: Fungitrap Building
category: entities
---

# Fungitrap Building

This document describes the `fungitrap_01.xml` entity, which represents a fungitrap building in Noita.

## Core Components

The fungitrap building is primarily defined by its Lua scripting and camera-bound properties.

### LuaComponent

This component links the building to its functional script.

| Attribute         | Value                                   | Description                                                                 |
| :---------------- | :-------------------------------------- | :-------------------------------------------------------------------------- |
| `script_source_file` | `data/scripts/buildings/fungitrap_01.lua` | The path to the Lua script that controls the fungitrap's behavior.          |
| `execute_every_n_frame` | `40`                                    | The script will execute its logic every 40 frames.                          |

### CameraBoundComponent

This component manages the entity's visibility and behavior based on camera proximity.

| Attribute   | Value   | Description                                                                                             |
| :---------- | :------ | :------------------------------------------------------------------------------------------------------ |
| `max_count` | `30`    | The maximum number of fungitrap entities that can be active within the camera's view.                   |
| `distance`  | `160000` | The squared distance from the camera within which the fungitrap entity will be considered active. |