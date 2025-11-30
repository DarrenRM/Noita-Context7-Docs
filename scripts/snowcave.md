---
title: snowcave
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/snowcave.lua
---

# snowcave

This file, `snowcave.lua`, defines the characteristics and entities that populate the "Snowcave" biome in the game Noita. It acts as a blueprint for how this specific area of the game world is generated, dictating the types of enemies, items, and environmental props that can appear within it. By registering spawn functions and defining probability tables for various entities, this script directly influences the player's experience in the Snowcave, contributing to its unique atmosphere and gameplay challenges.

## File Structure

The `snowcave.lua` file is structured as a Lua script. It primarily uses global tables to define spawnable entities and their associated properties. The core structure involves:

1.  **Initialization and Helper Functions:** The script begins by including other necessary Lua files (`dofile_once`) for game logic, biome management, and utility functions.
2.  **Spawn Function Registration:** A series of `RegisterSpawnFunction` calls associate specific hexadecimal identifiers (likely representing internal game events or biome states) with Lua functions. These functions are responsible for triggering the spawning of various elements within the biome.
3.  **Entity Probability Tables:** The bulk of the file consists of global tables (e.g., `g_small_enemies`, `g_items`, `g_skulls`). These tables are structured as arrays of objects, where each object defines:
    *   `prob`: A probability value that influences the likelihood of this entity or group of entities spawning.
    *   `min_count`: The minimum number of instances of the entity to spawn.
    *   `max_count`: The maximum number of instances of the entity to spawn.
    *   `entity`: The path to the `.xml` file defining the entity to spawn.
    *   `entities`: In some cases, this can be a nested table of entities, allowing for more complex spawn configurations (e.g., a group of different enemy types).
    *   `offset_y`: An optional vertical offset for spawning props.

The `total_prob` key in these tables appears to be a running sum of probabilities, likely used internally by the game engine for probability calculations.

## Key Patterns

Several key patterns are evident in the sampled content:

*   **Categorization of Spawns:** Entities are grouped into logical categories, such as `g_small_enemies`, `g_unique_enemy`, `g_items`, and `g_skulls`. This organization makes it easier to manage and understand the different types of content within the biome.
*   **Probabilistic Spawning:** The use of `prob`, `min_count`, and `max_count` is a consistent pattern for all spawnable entities. This allows for dynamic and varied encounters, preventing each playthrough from being identical.
*   **Entity Definition by XML:** All spawnable entities are defined by external `.xml` files, referenced by their file paths. This modular approach allows for easy modification and addition of new entities without altering the core Lua scripts.
*   **Conditional Spawning:** The presence of a function within `g_scavenger_party` that checks the game's date (`GameGetDateAndTimeLocal`) indicates that some spawns might be tied to specific in-game events or time periods.
*   **Hierarchical Entity Spawning:** The `g_scavenger_party` example demonstrates a nested structure where a primary entity (`scavenger_leader.xml`) can be accompanied by a group of other entities with their own spawn counts.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. `g_small_enemies` Table Entry:**

```lua
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 2,    
		entity 	= "data/entities/animals/shotgunner.xml"
	},
```

*   **Explanation:** This entry defines a potential spawn for "small enemies" within the Snowcave. There's a 20% chance (`prob = 0.2`) for this specific entry to be chosen. If chosen, the game will attempt to spawn between 1 and 2 instances (`min_count = 1`, `max_count = 2`) of the `shotgunner` enemy, which is defined in `data/entities/animals/shotgunner.xml`.

**2. `g_scavenger_party` Table Entry:**

```lua
g_scavenger_party =
{
	total_prob = 0,
	{
		prob   		= 1,
		min_count	= 1,
		max_count	= 1,    
		entities 	= {
			{
				min_count	= 1,
				max_count 	= 3,
				entity = "data/entities/animals/scavenger_smg.xml",
			},
			{
				min_count	= 1,
				max_count 	= 3,
				entity = "data/entities/animals/scavenger_grenade.xml",
			},
			{
				min_count	= 0,
				max_count 	= 1,
				entity = "data/entities/animals/coward.xml",
			},
			"data/entities/animals/scavenger_leader.xml",
		}
	},
}
```

*   **Explanation:** This defines a specific "unique encounter" called a scavenger party. With a probability of 1 (`prob = 1`), a single instance of this encounter will be triggered. This encounter is composed of a group of entities: a `scavenger_leader.xml`, and a variable number of `scavenger_smg.xml`, `scavenger_grenade.xml`, and `coward.xml` entities. This demonstrates how multiple entities can be grouped together for a single spawn event.

**3. `g_items` Table Entry:**

```lua
	{
		prob   		= 5,
		min_count	= 1,
		max_count	= 1,    
		entity 	= "data/entities/items/wand_level_02.xml"
	},
```

*   **Explanation:** This entry from the `g_items` table indicates that there's a chance to spawn a level 2 wand. The `prob` value of `5` is likely on a different scale than the enemy probabilities, suggesting a different weighting system for items. If this spawn is selected, one `wand_level_02.xml` will be placed in the biome.

## Reference

This file contains 1243 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/snowcave.lua).

---