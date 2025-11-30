---
title: Trailer Entity
category: entities
---

# Trailer Entity

This entity is designed to be used for trailer sequences within Noita. It primarily relies on a Lua script to manage its behavior.

## Key Components

### LuaComponent

This is the core component responsible for the entity's functionality.

*   **`script_source_file`**: Specifies the path to the Lua script that controls the entity's behavior.
    *   Value: `data/entities/trailer/trailer.lua`
*   **`vm_type`**: Determines how the Lua virtual machine is managed.
    *   Value: `ONE_PER_COMPONENT_INSTANCE` (Each instance of this component gets its own VM)
*   **`enable_coroutines`**: Enables the use of coroutines within the Lua script.
    *   Value: `1` (Enabled)
*   **`execute_on_added`**: Indicates whether the script should execute immediately when the entity is added to the game.
    *   Value: `1` (Execute on added)
*   **`execute_every_n_frame`**: Controls the frame rate at which the script executes.
    *   Value: `-1` (This typically means it runs once or is controlled by other script logic, not a fixed frame interval)
*   **`execute_times`**: Specifies how many times the script should execute.
    *   Value: `1` (Executes only once)

## Tags

*   **`trailer`**: This tag likely identifies the entity as part of a trailer sequence, potentially for internal game logic or modding identification.