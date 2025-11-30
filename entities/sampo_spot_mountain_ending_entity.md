---
title: Sampo Spot Mountain Ending Entity
category: entities
---

# Sampo Spot Mountain Ending Entity

This entity defines a specific point in the game world related to the "Sampo Spot Mountain" ending. It primarily utilizes a Lua script to manage its behavior.

## Key Components

### LuaComponent

This component is responsible for executing custom game logic.

*   **`_enabled`**: `1` (Indicates the component is active).
*   **`execute_every_n_frame`**: `240` (The associated script will execute every 240 frames).
*   **`script_source_file`**: `data/scripts/magic/altar_tablet_magic.lua` (Specifies the Lua script file that controls the entity's behavior).

### VariableStorageComponent

This component stores persistent variables associated with the entity.

*   **`name`**: `tablets_eaten` (The name of the variable).
*   **`value_int`**: `0` (The initial integer value of the variable, likely tracking the number of "tablets eaten" for the ending condition).