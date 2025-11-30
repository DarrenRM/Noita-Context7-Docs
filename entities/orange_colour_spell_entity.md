---
title: Orange Colour Spell Entity
category: entities
---

# Orange Colour Spell Entity

This entity defines the "orange" colour spell in Noita. It primarily utilizes Lua components to execute specific scripts and stores the colour name as a variable.

## Key Components

### LuaComponent (Execute Every N Frame)

This component executes a Lua script every specified number of frames.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - The script responsible for the spell's behaviour.
*   **`execute_every_n_frame`**: `1` - The script will execute on every frame.
*   **`remove_after_executed`**: `1` - The component will be removed after its first execution.

### LuaComponent (Execute On Added)

This component executes a Lua script when the entity is added to the game world.

*   **`script_source_file`**: `data/scripts/projectiles/colour_spell.lua` - The script responsible for the spell's behaviour.
*   **`execute_on_added`**: `1` - The script will execute when the entity is added.
*   **`remove_after_executed`**: `1` - The component will be removed after its first execution.

### VariableStorageComponent

This component stores a variable associated with the entity.

*   **`name`**: `colour_name` - The name of the variable.
*   **`value_string`**: `orange` - The string value assigned to the variable, identifying this as the orange colour spell.

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
		value_string="orange">
	</VariableStorageComponent>
</Entity>
```