---
title: Effect Nukes Entity
category: guides
---

<Entity>
	<InheritTransformComponent />
	<LuaComponent
		script_source_file="data/scripts/streaming_integration/scripts/effect_nukes.lua"
		execute_every_n_frame="3" />
	<LifetimeComponent
		lifetime="300" />
</Entity>
```

---
title: Effect Nukes Entity
category: entities
---

# Effect Nukes Entity

This entity defines a special effect related to "nukes" within the game. It primarily relies on a Lua script for its behavior and has a defined lifespan.

## Key Components

### LuaComponent

This component is responsible for the entity's dynamic behavior, executing a specific Lua script.

*   **`script_source_file`**: Specifies the path to the Lua script that controls the entity's logic.
    *   `data/scripts/streaming_integration/scripts/effect_nukes.lua`
*   **`execute_every_n_frame`**: Determines how frequently the Lua script is executed.
    *   `3`: The script runs every 3 frames.

### LifetimeComponent

This component dictates how long the entity will exist before being removed from the game.

*   **`lifetime`**: The duration in frames the entity will persist.
    *   `300`: The entity will last for 300 frames.

### InheritTransformComponent

This component indicates that the entity will inherit transformation properties (like position, rotation, scale) from its parent or the environment it's spawned in. This is a common component for entities that don't have their own independent transform.