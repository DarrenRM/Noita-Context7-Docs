---
title: Effect - Slow Bullets
category: scripts
---

# Effect - Slow Bullets

This entity defines a visual and functional effect that slows down projectiles within its area of influence.

## Lua Component

This component links the entity to its associated Lua script, which handles the actual logic for slowing bullets.

### Key Attributes

*   `script_source_file`: Specifies the path to the Lua script responsible for the effect's behavior.
*   `execute_every_n_frame`: Determines how frequently the Lua script's logic is executed. A lower number means more frequent execution.

## Lifetime Component

This component dictates how long the effect will persist.

### Key Attributes

*   `lifetime`: The duration of the effect in frames.

```xml
<Entity >
	<InheritTransformComponent />
   
	<LuaComponent
		script_source_file="data/scripts/streaming_integration/scripts/effect_slow_bullets.lua"
		execute_every_n_frame="3"
		>
	</LuaComponent>
	
	<LifetimeComponent
		lifetime="1800"
		>
	</LifetimeComponent>
  
</Entity>
```