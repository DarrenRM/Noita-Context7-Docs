---
title: Tower Check Entity
category: entities
---

# Tower Check Entity

This entity is a simple placeholder used to trigger a Lua script for checking tower conditions. It doesn't have any visual representation or direct gameplay impact on its own.

## Key Components

### LuaComponent
This is the primary component responsible for executing the associated Lua script.

*   **`script_source_file`**: `data/scripts/magic/towercheck.lua`
    *   Specifies the path to the Lua script that will be executed. This script likely contains the logic for checking tower-related conditions.
*   **`execute_every_n_frame`**: `1`
    *   Indicates that the script should be executed every single frame, ensuring continuous monitoring or immediate reaction to any changes.

## Usage

This entity is typically placed in a level or area where specific tower-related logic needs to be managed by the `towercheck.lua` script. Its presence is purely functional, serving as an anchor for the script's execution.