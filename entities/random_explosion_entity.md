---
title: Random Explosion Entity
category: entities
---

# Random Explosion Entity

This entity defines a simple, self-contained explosion effect that is triggered by a Lua script. It's designed to be a reusable component for creating various explosive events within the game.

## Key Components

### LuaComponent

This is the primary component responsible for the entity's behavior.

*   **`script_source_file`**: Specifies the Lua script that controls the explosion's logic. In this case, it points to `data/scripts/projectiles/random_explosion.lua`.
*   **`execute_on_added`**: When set to `1`, the script will execute immediately after the entity is added to the game world.
*   **`remove_after_executed`**: When set to `1`, the entity will be automatically removed from the game world once its script has finished executing.

## Usage

This entity is typically instantiated by other game elements (e.g., projectiles, traps, or other scripts) to create an explosion effect at a specific location. The actual visual and functional aspects of the explosion are determined by the `random_explosion.lua` script.

```xml
<Entity>
	<LuaComponent 
		_enabled="1" 
		script_source_file="data/scripts/projectiles/random_explosion.lua"
		execute_on_added="1"
		remove_after_executed="1">
   </LuaComponent>
</Entity>
```