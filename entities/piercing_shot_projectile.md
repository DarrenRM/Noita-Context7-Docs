---
title: Piercing Shot Projectile
category: entities
---

# Piercing Shot Projectile

This entity defines a projectile with piercing capabilities, managed by a Lua script.

## Key Components

### LuaComponent
This component is responsible for the projectile's behavior.

*   **script\_source\_file**: `data/scripts/projectiles/piercing_shot.lua` - Specifies the Lua script that controls the projectile's logic.
*   **execute\_every\_n\_frame**: `1` - The script will execute every frame.
*   **remove\_after\_executed**: `1` - The projectile entity will be removed after the script has executed once.

```xml
<Entity>
	<LuaComponent
		script_source_file="data/scripts/projectiles/piercing_shot.lua"
		execute_every_n_frame="1"
		remove_after_executed="1">
	</LuaComponent>
</Entity>
```