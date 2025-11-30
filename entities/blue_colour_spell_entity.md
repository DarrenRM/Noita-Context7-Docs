---
title: Blue Colour Spell Entity
category: entities
---

# Blue Colour Spell Entity

This entity defines the "blue" colour spell in Noita, primarily used for projectile effects. It leverages Lua scripts to manage its behavior and stores its colour name as a variable.

## Key Components

### LuaComponent

This component is responsible for executing Lua scripts associated with the entity.

*   **`script_source_file`**: Specifies the Lua script to be executed. In this case, it's `data/scripts/projectiles/colour_spell.lua`. This script likely handles the visual and functional aspects of the colour spell when applied to projectiles.
*   **`execute_every_n_frame`**: If present, the script will execute every `n` frames. This is used for ongoing effects.
*   **`execute_on_added`**: If present, the script will execute once when the entity is added to the game world.
*   **`remove_after_executed`**: If set to `1`, the `LuaComponent` will be removed from the entity after its script has executed (either once or after its `execute_every_n_frame` condition is met).

### VariableStorageComponent

This component stores key-value pairs of variables associated with the entity.

*   **`name`**: The name of the variable. Here, it's `colour_name`.
*   **`value_string`**: The string value assigned to the variable. For this entity, it's `"blue"`, clearly identifying the colour associated with this spell.