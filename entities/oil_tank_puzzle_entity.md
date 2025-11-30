---
title: Oil Tank Puzzle Entity
category: entities
---

# Oil Tank Puzzle Entity

This entity represents an oil tank used in puzzles within Noita. It primarily utilizes `MaterialAreaCheckerComponent` and `LuaComponent` to manage its behavior.

## Key Components

### MaterialAreaCheckerComponent

This component monitors a specific area for the presence of certain materials.

| Attribute           | Description                                                                 |
| :------------------ | :-------------------------------------------------------------------------- |
| `area_aabb.min_x`   | Minimum X-coordinate of the area to check.                                  |
| `area_aabb.max_x`   | Maximum X-coordinate of the area to check.                                  |
| `area_aabb.min_y`   | Minimum Y-coordinate of the area to check.                                  |
| `area_aabb.max_y`   | Maximum Y-coordinate of the area to check.                                  |
| `update_every_x_frame` | How often (in frames) the checker updates.                                  |
| `material`          | The primary material to look for.                                           |
| `material2`         | A secondary material to look for.                                           |
| `look_for_failure`  | Whether to trigger on failure to find materials (0 = no, 1 = yes).          |
| `kill_after_message` | Whether to kill the entity after a message is displayed (0 = no, 1 = yes). |

### LuaComponent (Initialization)

This component executes a Lua script to initialize the puzzle.

| Attribute             | Description                                                                 |
| :-------------------- | :-------------------------------------------------------------------------- |
| `script_source_file`  | Path to the Lua script for initialization.                                  |
| `execute_every_n_frame` | How often (in frames) the script executes.                                  |
| `execute_times`       | The total number of times the script will execute.                          |

### LuaComponent (Success Check)

This component executes a Lua script to check for puzzle success.

| Attribute                           | Description                                                                 |
| :---------------------------------- | :-------------------------------------------------------------------------- |
| `script_material_area_checker_success` | Path to the Lua script that handles success conditions for the material checker. |

## XML Structure

```xml
<Entity>
	<MaterialAreaCheckerComponent
		area_aabb.min_x="-4" 
		area_aabb.max_x="4" 
		area_aabb.min_y="4"   
		area_aabb.max_y="5" 
		update_every_x_frame="1"
		material="oil"
		material2="oil"
		look_for_failure="0"
		kill_after_message="1">
	</MaterialAreaCheckerComponent>

	<LuaComponent
		script_source_file="data/scripts/buildings/oiltank_puzzle_init.lua"
		execute_every_n_frame="4"
		execute_times="100"
		>
	</LuaComponent>

	<LuaComponent
		script_material_area_checker_success="data/scripts/buildings/oiltank_puzzle_check.lua" >
	</LuaComponent>
</Entity>
```