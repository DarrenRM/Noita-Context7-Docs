---
title: Game Reset Debug Entity
category: entities
---

# Game Reset Debug Entity

This entity is a simple debug tool designed to reset the game state. It achieves this by executing a Lua script when it is added to the game world.

## Key Components

### LuaComponent

This component is responsible for executing Lua scripts.

*   **`script_source_file`**: Specifies the path to the Lua script to be executed.
    *   Value: `data/entities/_debug/game_reset.lua`
*   **`execute_on_added`**: Determines if the script should run when the entity is added.
    *   Value: `1` (True - the script will execute on entity addition)
*   **`execute_every_n_frame`**: Controls how often the script runs in frames.
    *   Value: `-1` (This means it will not execute repeatedly based on frames, as `execute_times` is set to 1).
*   **`execute_times`**: Defines how many times the script should be executed.
    *   Value: `1` (The script will run only once).

---
```xml
<Entity>	
	<LuaComponent
		script_source_file="data/entities/_debug/game_reset.lua"
		execute_on_added="1"
		execute_every_n_frame="-1"
		execute_times="1" >
	</LuaComponent>
</Entity>
```