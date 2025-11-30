---
title: Funroom Check Building
category: entities
---

# Funroom Check Building

This entity represents a building used for checking funroom conditions in Noita. It primarily relies on a Lua script to perform its logic.

## Key Components

### LuaComponent
This is the core component that defines the behavior of the `funroom_check` building.

*   **`script_source_file`**: Specifies the path to the Lua script responsible for the building's functionality.
    *   Value: `data/scripts/buildings/funroom_check.lua`
*   **`execute_every_n_frame`**: Determines how frequently the Lua script's logic is executed.
    *   Value: `5` (The script will run every 5 frames).