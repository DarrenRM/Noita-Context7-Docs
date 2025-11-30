---
title: Bunker Check Entity
category: entities
---

---

# Bunker Check Entity

This entity defines a "bunker check" mechanism, likely used for game logic or progression within Noita. It primarily relies on a Lua component to execute custom scripting.

## Entity Definition

The core of this entity is a simple XML structure defining its properties and components.

```xml
<Entity tags="bunker_check">
	<LuaComponent
		script_source_file="data/scripts/buildings/bunker_check.lua"
		execute_every_n_frame="20"
		>
	</LuaComponent>
</Entity>
```

## Key Components

### LuaComponent

This component is responsible for executing custom Lua scripts associated with the bunker check.

*   **`script_source_file`**: Specifies the path to the Lua script file that will be executed.
    *   Value: `data/scripts/buildings/bunker_check.lua`
*   **`execute_every_n_frame`**: Determines how frequently the Lua script will be executed.
    *   Value: `20` (The script will run every 20 frames).

## Tags

*   **`bunker_check`**: This tag likely identifies the entity as part of a bunker-related system or logic.

## Associated Scripts

*   **`data/scripts/buildings/bunker_check.lua`**: This Lua script contains the actual logic for the bunker check. Its specific functionality would need to be examined within the script file itself.