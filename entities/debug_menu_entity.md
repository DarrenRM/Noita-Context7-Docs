---
title: Debug Menu Entity
category: entities
---

# Debug Menu Entity

This entity provides access to the Noita debug menu, allowing for in-game manipulation and testing.

## Core Components

### LuaComponent

This component is responsible for the functionality of the debug menu.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script that implements the debug menu logic.                |
| `vm_type`           | Specifies the virtual machine type for the script. `ONE_PER_COMPONENT_INSTANCE` ensures a unique VM for this component. |
| `enable_coroutines` | Enables coroutine support within the Lua script, allowing for asynchronous operations. |
| `execute_on_added`  | The script will execute immediately after the entity is added to the game world. |
| `execute_times`     | The script will execute only once.                                          |

```xml
<Entity tags="debug_menu">	

	<LuaComponent
		script_source_file="data/entities/_debug/debug_menu.lua"
		vm_type="ONE_PER_COMPONENT_INSTANCE"
		enable_coroutines="1"
		execute_on_added="1"
		execute_every_n_frame="-1"
		execute_times="1" >
	</LuaComponent>
	
</Entity>
```