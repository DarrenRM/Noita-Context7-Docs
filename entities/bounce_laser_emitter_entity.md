---
title: Bounce Laser Emitter Entity
category: entities
---

# Bounce Laser Emitter Entity

This entity defines a projectile that emits a bouncing laser.

## Lua Component

The core functionality of this entity is handled by a Lua script.

### `LuaComponent`

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `script_source_file` | Path to the Lua script responsible for the entity's behavior.               |
| `execute_every_n_frame` | How often the script logic is executed (1 means every frame).               |
| `remove_after_executed` | Whether the entity should be removed after the script has executed once.    |

```xml
<Entity>
	<LuaComponent
		script_source_file="data/scripts/projectiles/bounce_laser_emitter.lua"
		execute_every_n_frame="1"
		remove_after_executed="1"
	>
	</LuaComponent>
</Entity>
```