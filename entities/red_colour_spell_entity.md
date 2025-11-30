---
title: Red Colour Spell Entity
category: entities
---

# Red Colour Spell Entity

This entity defines the "red" colour spell in Noita, primarily through its Lua components and variable storage. It's designed to be a projectile that applies a specific colour effect.

## Key Components

### LuaComponent (Execution on Add)

This component is responsible for executing a Lua script when the entity is added to the game world.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - This points to the core script that handles the spell's behaviour.
*   **`execute_on_added`**: `1` - Ensures the script runs immediately upon the entity's creation.
*   **`remove_after_executed`**: `1` - The component (and likely the entity) is removed after the script has finished its execution.

### LuaComponent (Execution Every N Frames)

This component also utilizes the same Lua script but executes it repeatedly.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - Same script as above, indicating it might handle ongoing effects or updates.
*   **`execute_every_n_frame`**: `1` - The script will execute on every single frame the entity exists.
*   **`remove_after_executed`**: `1` - The component is removed after the script has finished its execution. This might imply the script itself has logic to determine when to stop executing.

### VariableStorageComponent

This component stores a specific variable associated with the entity.

*   **`name`**: `colour_name` - The name of the variable being stored.
*   **`value_string`**: `red` - The string value assigned to `colour_name`, clearly identifying this entity as the "red" colour spell.

## Summary

The `colour_red.xml` entity is a simple projectile entity that leverages `colour_spell.lua` to define its behaviour. The `VariableStorageComponent` explicitly tags it as the "red" colour spell, allowing other game systems to identify and utilize its specific properties. The two `LuaComponent` instances suggest that the `colour_spell.lua` script handles both the initial application of the colour effect and potentially any ongoing visual or functional aspects of the red colour.