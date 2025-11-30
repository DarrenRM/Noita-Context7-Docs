---
title: excavationsite
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/excavationsite.lua
---

# excavationsite

The `excavationsite.lua` file defines the configuration and content for the "Excavation Site" biome in Noita. This biome is a distinct area within the game's world, and this script dictates what entities, structures, and visual elements can spawn within it. It acts as a blueprint for generating this specific part of the game's procedurally generated levels, influencing enemy placement, environmental features, and potential loot.

## File Structure

This file is written in Lua and primarily uses tables to define various aspects of the Excavation Site biome. The structure is organized around defining different types of spawns and environmental elements.

Key structural elements observed:

*   **Global Variables:** The file starts with some global constants and includes for other Lua scripts (`CHEST_LEVEL`, `dofile_once`, `dofile`).
*   **`RegisterSpawnFunction`:** This function is used to associate specific hexadecimal color codes with Lua functions that handle spawning particular entities or scene elements. This is a core mechanism for defining what can appear in the biome based on its underlying "pixel scene" data.
*   **Enemy/Entity Tables:** The bulk of the file consists of tables that define lists of entities to be spawned. These tables are typically named with a `g_` prefix followed by a descriptive name (e.g., `g_small_enemies`, `g_unique_enemy2`).
    *   Each of these tables has a `total_prob` field, which seems to be a cumulative probability or a normalization factor.
    *   Inside these tables, individual spawn entries are defined as sub-tables.
    *   **Common fields within spawn entries:**
        *   `prob`: The probability of this specific entry being chosen for spawning.
        *   `min_count`: The minimum number of entities to spawn if this entry is selected.
        *   `max_count`: The maximum number of entities to spawn if this entry is selected.
        *   `entity`: The path to the `.xml` file defining the entity to spawn.
        *   `material_file`: (Often seen in biome-specific structures) The path to a `.png` file defining the material layer of a specific biome element.
        *   `visual_file`: (Often seen in biome-specific structures) The path to a `.png` file defining the visual layer of a specific biome element.
        *   `background_file`: (Often seen in biome-specific structures) The path to a `.png` file defining the background layer of a specific biome element.
        *   `is_unique`: A flag (0 or 1) indicating if this element is intended to be unique within a certain context.
        *   `spawn_check`: (Optional) A Lua function that returns `true` or `false`, determining if the entity should spawn based on game conditions.

## Key Patterns

*   **Color-to-Function Mapping:** The `RegisterSpawnFunction` calls establish a direct link between specific colors in the biome's underlying pixel data and the game's spawning logic. This is a fundamental way Noita defines biome features.
*   **Probabilistic Spawning:** Most spawn entries use a `prob` field, indicating that the game randomly selects entities to spawn based on these probabilities. The `total_prob` field likely helps normalize these probabilities.
*   **Enemy Groupings:** Enemies are often grouped into tables like `g_small_enemies`, suggesting different categories or tiers of enemies that can appear in the biome.
*   **Biome-Specific Assets:** Many entries reference `.png` files within `data/biome_impl/excavationsite/`, indicating that the Excavation Site biome has its own unique set of visual and material assets for structures and environmental features.
*   **Conditional Spawning:** The `spawn_check` function demonstrates a pattern for implementing conditional spawning, allowing entities to appear only under specific game circumstances (e.g., during a particular time of year).
*   **Variations of Scenes:** The presence of entries like `load_pixel_scene4` and `load_pixel_scene4_alt`, and corresponding tables like `g_pixel_scene_04_alt`, suggests that the Excavation Site biome can have variations in its layout and content.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `g_small_enemies` Table:**

```lua
g_small_enemies =
{
	total_prob = 0,
	-- this is air, so nothing spawns at 0.6
	{
		prob   		= 0.55,
		min_count	= 0,
		max_count	= 0,    
		entity 	= ""
	},
	-- add skullflys after this step
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 3,    
		entity 	= "data/entities/animals/firebug.xml"
	},
	-- ... other enemy entries
}
```

*   **Explanation:** This table defines a pool of smaller enemies that can spawn in the Excavation Site. The first entry with `prob = 0.55` and `entity = ""` likely represents a "no spawn" condition for a portion of the probability space, possibly related to air or empty space. Subsequent entries define specific enemies like `firebug.xml`, `rat.xml`, etc., with their respective spawn probabilities and counts.

**2. `g_unique_enemy2` with `spawn_check`:**

```lua
g_unique_enemy3 =
{
	total_prob = 0,
	-- this is air, so nothing spawns at 0.6
	{
		prob   		= 0.5,
		min_count	= 0,
		max_count	= 0,    
		entity 	= ""
	},
	-- add skullflys after this step
	{
		prob   		= 0.5,
		min_count	= 1,
		max_count	= 1,    
		entity 	= "data/entities/animals/miner_santa.xml",
		spawn_check = function() 
			local year, month, day = GameGetDateAndTimeLocal()
			
			if ( month == 12 ) and ( day >= 24 ) and ( day <= 26 ) then
				return true
			else
				return false 
			end
		end
	},
	-- ... other entries
}
```

*   **Explanation:** This entry showcases a conditional spawn. The `miner_santa.xml` entity will only spawn if the `spawn_check` function returns `true`. This function checks if the current local date is between December 24th and December 26th, implying a special holiday-themed enemy that appears only during that period.

**3. Biome Structure Definition (`g_machine_pool` or similar):**

```lua
-- (Example based on observed patterns, actual table name might vary)
g_machine_pool =
{
	total_prob = 0,
	{
		prob   			= 0.3,
		material_file 	= "data/biome_impl/excavationsite/machine_6.png",
		visual_file		= "data/biome_impl/excavationsite/machine_6_visual.png",
		background_file	= "",
		is_unique		= 0
	},
	-- ... other machine/structure entries
}
```

*   **Explanation:** This type of table defines specific environmental structures or features within the Excavation Site. It uses `material_file`, `visual_file`, and `background_file` to specify the graphical assets that make up these structures. The `prob` determines how likely this particular structure is to be placed.

## Reference

This file contains 1181 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/excavationsite.lua).

---