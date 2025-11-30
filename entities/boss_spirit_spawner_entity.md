---
title: Boss Spirit Spawner Entity
category: entities
---

# Boss Spirit Spawner Entity

This entity is responsible for spawning the Boss Spirit in Noita. It utilizes a Lua script to manage its spawning behavior.

## Key Components

### LuaComponent

This component defines the script that controls the spawner's logic.

*   **`script_source_file`**: Specifies the path to the Lua script responsible for the spawner's behavior.
    *   Value: `data/entities/animals/boss_spirit/spawner.lua`
*   **`execute_every_n_frame`**: Determines how often the Lua script's logic is executed.
    *   Value: `180` (This means the script will run every 180 frames, which is approximately every 3 seconds at 60 FPS).

## Entity Structure

The entity is a simple container with a single `LuaComponent` to manage its functionality.

```xml
<Entity tags="" serialize="1">

	<LuaComponent 
		script_source_file="data/entities/animals/boss_spirit/spawner.lua"
		execute_every_n_frame="180"
	>
	</LuaComponent>
</Entity>
```