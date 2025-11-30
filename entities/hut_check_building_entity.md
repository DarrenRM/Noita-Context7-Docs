---
title: Hut Check Building Entity
category: entities
---

# Hut Check Building Entity

This entity defines a "hut check" building, primarily used for triggering events or loading specific entities within the game world. It utilizes a Lua component for custom logic and a `LoadEntitiesComponent` to spawn other entities.

## Key Components

### LuaComponent

This component enables custom scripting for the building.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`  | Path to the Lua script that controls the building's behavior.               |
| `execute_every_n_frame` | Determines how often the Lua script's logic is executed (in game frames). |

### LoadEntitiesComponent

This component is responsible for loading other entities into the game world when this building is active.

| Attribute     | Description                                                                                             |
| :------------ | :------------------------------------------------------------------------------------------------------ |
| `entity_file` | The path to the entity XML file to be loaded.                                                           |
| `kill_entity` | A flag indicating whether the current building entity should be destroyed after loading the specified entity (0 means it remains). |
| `count.min`   | The minimum number of entities to load.                                                                 |
| `count.max`   | The maximum number of entities to load.                                                                 |

## Example Usage

The provided XML snippet shows a `hut_check` entity that:
- Executes a Lua script located at `data/scripts/buildings/hut_check.lua` every 20 frames.
- Loads one instance of the `book_bunker.xml` entity file.
- The `hut_check` building itself is not destroyed after loading the `book_bunker`.

```xml
<Entity tags="hut_check">
	<LuaComponent
		script_source_file="data/scripts/buildings/hut_check.lua"
		execute_every_n_frame="20"
		>
	</LuaComponent>
		
	<LoadEntitiesComponent 
		entity_file="data/entities/items/books/book_bunker.xml"
		kill_entity="0"
		count.min="1"
        count.max="1"
		>
	</LoadEntitiesComponent>
</Entity>
```