---
title: Rainbow Colour Spell Entity
category: entities
---

# Rainbow Colour Spell Entity

This entity defines the "rainbow" colour effect for spells in Noita. It primarily utilizes Lua components to manage its behavior and a VariableStorageComponent to identify its specific colour.

## Key Components

### LuaComponent (Execution)

This component is responsible for executing the `colour_spell.lua` script.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - Specifies the Lua script to be executed.
*   **`execute_every_n_frame`**: `1` - The script will execute every frame.
*   **`remove_after_executed`**: `1` - The Lua component will be removed after its execution.

### LuaComponent (Added)

This component also executes the `colour_spell.lua` script, but specifically when the entity is added.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - Specifies the Lua script to be executed.
*   **`execute_on_added`**: `1` - The script will execute when the entity is added to the game.
*   **`remove_after_executed`**: `1` - The Lua component will be removed after its execution.

### VariableStorageComponent

This component stores a variable that identifies the specific colour.

*   **`name`**: `colour_name` - The name of the variable.
*   **`value_string`**: `rainbow` - The string value, indicating this entity represents the "rainbow" colour.