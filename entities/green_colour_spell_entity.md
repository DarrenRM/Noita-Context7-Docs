---
title: Green Colour Spell Entity
category: entities
---

# Green Colour Spell Entity

This entity defines the "green" colour spell, primarily used for projectile effects. It leverages Lua scripts to manage its behavior.

## Key Components

### LuaComponent

This component is responsible for executing Lua scripts associated with the entity.

*   **`script_source_file`**: Specifies the path to the Lua script to be executed.
    *   `data/scripts/projectiles/colour_spell.lua`: This script likely handles the visual and functional aspects of colour spells as projectiles.
*   **`execute_every_n_frame`**: If set, the script will execute every `n` frames.
    *   `1`: The script executes every frame.
*   **`execute_on_added`**: If set to `1`, the script will execute once when the entity is added to the game world.
*   **`remove_after_executed`**: If set to `1`, the Lua component will be removed after its script has executed. This is useful for one-time effects.

### VariableStorageComponent

This component stores variables associated with the entity.

*   **`name`**: The name of the variable.
    *   `colour_name`: Identifies this variable as storing the colour name.
*   **`value_string`**: The string value of the variable.
    *   `green`: This specific entity is designated as the "green" colour spell.

## Summary

The `colour_green.xml` entity is a simple configuration that attaches a Lua script (`colour_spell.lua`) to itself and stores the string "green" as a variable. This setup is designed to enable the "green" colour spell functionality within Noita, likely by having the `colour_spell.lua` script interpret the `colour_name` variable to apply specific effects. The `remove_after_executed="1"` attribute suggests that the spell's primary effect is applied once, rather than being a persistent entity.