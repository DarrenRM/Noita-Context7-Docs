---
title: Essence to Power Conversion
category: entities
---

---

# Essence to Power Conversion

This entity defines a mechanism for converting "essence" into "power" within the game. It utilizes a Lua script to handle the conversion logic.

## Key Components

### LuaComponent

This component is responsible for executing custom game logic.

*   **`script_source_file`**: Specifies the Lua script file that contains the conversion logic.
    *   Value: `data/scripts/projectiles/essence_to_power.lua`
*   **`execute_every_n_frame`**: Determines how often the script is executed.
    *   Value: `1` (executes every frame)
*   **`remove_after_executed`**: Indicates whether the entity should be removed after the script has been executed.
    *   Value: `1` (entity is removed after execution)

## Associated Script

The core functionality of this entity is handled by the `data/scripts/projectiles/essence_to_power.lua` script. This script would contain the specific game rules for how essence is detected, collected, and transformed into power.