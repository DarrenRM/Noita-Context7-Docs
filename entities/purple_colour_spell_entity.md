---
title: Purple Colour Spell Entity
category: entities
---

# Purple Colour Spell Entity

This entity defines the "purple" colour spell in Noita, primarily through its Lua components and variable storage. It's designed to be a projectile that executes a specific script and stores its colour name.

## Key Components

### LuaComponent (Script Execution)

This component is responsible for executing Lua scripts associated with the entity.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua`
    *   This indicates the primary script file that handles the spell's logic.
*   **`execute_every_n_frame`**: `1`
    *   The script will execute every single frame.
*   **`execute_on_added`**: `1`
    *   The script will execute once when the entity is first added to the game.
*   **`remove_after_executed`**: `1`
    *   The Lua component will be removed from the entity after its script has been executed.

There are two instances of this component, one for `execute_every_n_frame` and one for `execute_on_added`, both pointing to the same script.

### VariableStorageComponent

This component stores a specific variable for the entity.

*   **`name`**: `colour_name`
    *   The name of the variable being stored.
*   **`value_string`**: `purple`
    *   The string value assigned to the `colour_name` variable, identifying this entity as the "purple" spell.

```xml
<Entity>
	<LuaComponent
		script_source_file="data/scripts/projectiles/colour_spell.lua"
		execute_every_n_frame="1"
		remove_after_executed="1">
	</LuaComponent>
	<LuaComponent
		script_source_file="data/scripts/projectiles/colour_spell.lua"
		execute_on_added="1"
		remove_after_executed="1">
	</LuaComponent>
	<VariableStorageComponent
		name="colour_name"
		value_string="purple">
	</VariableStorageComponent>
</Entity>
```