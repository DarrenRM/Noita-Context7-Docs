---
title: Curse Initialization Entity
category: entities
---

# Curse Initialization Entity

This entity is responsible for initializing curse effects within the game. It primarily relies on a Lua script to manage its behavior.

## Key Components

### LuaComponent

This component links the entity to its associated Lua script, which handles the logic for curse initialization.

*   **`script_source_file`**: Specifies the path to the Lua script responsible for the curse's behavior.
    *   Value: `data/scripts/projectiles/curse_init.lua`
*   **`execute_every_n_frame`**: Determines how frequently the script's logic is executed.
    *   Value: `1` (meaning it executes every frame)