---
title: Trailer Entity 2
category: entities
---

# Trailer Entity 2

This entity is a simple trailer entity, primarily controlled by a Lua script. It's designed to be executed once when added to the game.

## Key Components

### LuaComponent

This component is responsible for the entity's behavior.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script that governs the entity's logic.                     |
| `vm_type`           | Specifies the virtual machine type for the script. `ONE_PER_COMPONENT_INSTANCE` means each instance of this component gets its own VM. |
| `enable_coroutines` | Enables coroutine support within the Lua script.                            |
| `execute_on_added`  | If set to `1`, the script will execute immediately after the entity is added to the game. |
| `execute_every_n_frame` | Set to `-1`, indicating the script does not execute on a frame-by-frame basis. |
| `execute_times`     | Set to `1`, meaning the script will execute only once.                      |

## Entity Tags

| Tag    | Description                                                                 |
| :---- | :-------------------------------------------------------------------------- |
| `trailer` | This tag likely identifies the entity as part of a trailer or cinematic sequence. |