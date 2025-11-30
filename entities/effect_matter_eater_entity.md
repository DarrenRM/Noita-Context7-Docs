---
title: Effect Matter Eater Entity
category: entities
---

# Effect Matter Eater Entity

This entity defines the behavior of the "Matter Eater" effect in Noita, primarily managed through a Lua script.

## Key Components

### LuaComponent
This is the core component responsible for the entity's functionality.

*   **`script_shot`**: Specifies the Lua script that controls the entity's behavior.
    *   Value: `data/scripts/streaming_integration/scripts/matter_eater.lua`
*   **`execute_every_n_frame`**: Determines how often the script is executed.
    *   Value: `-1` (Indicates the script is likely executed once or on specific events, not on a fixed frame interval).

### LifetimeComponent
Manages how long the entity persists in the game world.

*   **`lifetime`**: The duration in seconds the entity will exist.
    *   Value: `3600` (Equivalent to 1 hour).

### InheritTransformComponent
This component is present but empty, suggesting it might be a placeholder or intended for future use, inheriting transform properties from its parent.

```xml
<Entity>
	
	<InheritTransformComponent>
    </InheritTransformComponent>	
    
    <LuaComponent
		script_shot="data/scripts/streaming_integration/scripts/matter_eater.lua"
		execute_every_n_frame="-1"
		>
	</LuaComponent>
	
	<LifetimeComponent
		lifetime="3600"
		>
	</LifetimeComponent>

</Entity>
```