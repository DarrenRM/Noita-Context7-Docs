---
title: Boss Wizard Spawner Entity
category: entities
---

# Boss Wizard Spawner Entity

This entity is responsible for spawning the boss wizard in Noita. It utilizes a Lua script to manage the spawning process.

## Key Components

### LuaComponent

This component is crucial for the entity's functionality, as it executes a Lua script to handle the spawning logic.

*   **`script_source_file`**: Specifies the path to the Lua script responsible for spawning the boss wizard.
    *   Value: `data/entities/animals/boss_wizard/spawn_wizard.lua`
*   **`execute_on_added`**: This attribute is set to `1`, indicating that the script should be executed immediately when the entity is added to the game world.

```xml
<Entity 
  name="$projectile_default" 
  tags=""
   >
	<LuaComponent
		script_source_file="data/entities/animals/boss_wizard/spawn_wizard.lua"
		execute_on_added="1"
		>
	</LuaComponent>
</Entity>
```