---
title: Greed Rain Entity
category: guides
---

<Entity tags="">
	<InheritTransformComponent />
	
	<LifetimeComponent
		lifetime="300"
		serialize_duration="1"
		>
	</LifetimeComponent>
	
	<LuaComponent 
        _enabled="1" 
        execute_every_n_frame="10"
        script_source_file="data/scripts/magic/greed_curse/spawn_meteors.lua" 
	>
    </LuaComponent>
</Entity>
```

---
title: Greed Rain Entity
category: entities
---

# Greed Rain Entity

This entity defines the "Greed Rain" effect, a magical curse that causes meteors to fall from the sky. It's primarily controlled by a Lua script that handles the spawning logic.

## Key Components

### `LifetimeComponent`

*   **`lifetime`**: `300` - The duration in frames this entity will exist.
*   **`serialize_duration`**: `1` - How long the entity's duration should be serialized.

### `LuaComponent`

*   **`_enabled`**: `1` - Ensures the Lua script is active.
*   **`execute_every_n_frame`**: `10` - The script will execute its logic every 10 frames.
*   **`script_source_file`**: `data/scripts/magic/greed_curse/spawn_meteors.lua` - This is the core of the entity's functionality, containing the logic for spawning meteors.

## Inheritance

*   **`InheritTransformComponent`**: This component suggests that the entity inherits transform properties, likely its position and rotation, from its parent or the context in which it's spawned.

## Purpose

The `greed_rain.xml` entity serves as a container for the logic that triggers and manages the Greed Rain curse. The actual visual and physical manifestation of the meteors is handled by the `spawn_meteors.lua` script.