---
title: crypt
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/crypt.lua
---

# crypt

This file, `crypt.lua`, is a crucial part of Noita's biome definition system. It specifically defines the characteristics, entities, and environmental elements that make up the "Crypt" biome. Biome definition files like this dictate what players will encounter in terms of enemies, props, visual effects, and overall atmosphere within a particular in-game area. This file contributes to the procedural generation of the game world by providing the building blocks for the Crypt.

## File Structure

The `crypt.lua` file is structured as a Lua script that registers various spawn functions and defines global tables containing lists of entities and their spawn probabilities. The primary structure involves:

1.  **`RegisterSpawnFunction` calls:** These lines associate specific hexadecimal color codes (likely representing areas or conditions within the game's generation system) with Lua functions that will be executed during biome generation. These functions are responsible for populating the biome with specific elements.
2.  **Global Tables for Entity Spawning:** The bulk of the file consists of global tables (e.g., `g_small_enemies`, `g_big_enemies`, `g_unique_enemy`, `g_beam`). Each table represents a category of entities or environmental features to be spawned within the Crypt biome.
3.  **Table Entries:** Within these global tables, individual entries define specific spawnable items. Each entry is a Lua table with the following common keys:
    *   `prob`: A floating-point number representing the probability of this entity spawning. Higher values mean a greater chance.
    *   `min_count`: The minimum number of this entity to spawn if selected.
    *   `max_count`: The maximum number of this entity to spawn if selected.
    *   `entity`: A string path to the `.xml` file defining the entity (e.g., an enemy, a prop).
    *   `entities`: An alternative to `entity`, this key holds a table of entity paths, allowing for multiple entities to be chosen from with the same probability.
    *   `ngpluslevel`: (Observed in one sample) Indicates the New Game+ level at which this entity becomes available.
    *   `offset_x`, `offset_y`: (Observed in one sample) Specifies an offset for the entity's spawn position.
    *   `material_file`: A string path to a `.png` file defining the material for a visual element (e.g., a beam).
    *   `visual_file`: A string path to a `.png` file defining the visual appearance of an element.
    *   `background_file`: A string path to a `.png` file for background elements.
    *   `is_unique`: A flag (0 or 1) indicating if the spawned element is unique.

The `total_prob` key at the beginning of each global table appears to be a running sum of probabilities, likely used internally by the game's spawning logic.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Categorization of Spawns:** Entities are clearly categorized into groups like `g_small_enemies`, `g_big_enemies`, and `g_unique_enemy`. This allows for distinct types of threats and encounters within the biome.
*   **Probability-Based Spawning:** The use of `prob`, `min_count`, and `max_count` is fundamental. This system allows for a dynamic and varied distribution of entities, ensuring that no two Crypt biomes are exactly alike.
*   **Entity Definition by XML:** All spawnable entities are defined by external `.xml` files, which contain their detailed properties, sprites, and behaviors. This Lua file acts as a configuration layer for these entities.
*   **Environmental Elements:** Beyond enemies, the file defines environmental features like `g_beam`, which likely control visual effects or hazards within the biome.
*   **Conditional Spawning:** The `RegisterSpawnFunction` calls, tied to hexadecimal color codes, suggest that specific spawn events are triggered based on the generated terrain or conditions.
*   **New Game+ Scaling:** The `ngpluslevel` key indicates that some entities are introduced or become more prevalent in later playthroughs, adding difficulty and variety.

## Sample Entries

Here are a few representative examples from the sampled content:

**1. Small Enemy Spawn Definition:**

```lua
	{
		prob   		= 0.3,
		min_count	= 3,
		max_count	= 4,    
		entity 	= "data/entities/animals/crypt/skullrat.xml"
	},
```

*   **Explanation:** This entry defines the "skullrat" enemy. It has a 30% chance (`prob = 0.3`) of spawning, and if it does, between 3 and 4 instances (`min_count = 3`, `max_count = 4`) will appear. The actual definition of the skullrat is in `data/entities/animals/crypt/skullrat.xml`.

**2. Unique Enemy/Prop Spawn Definition:**

```lua
	{
		prob   		= 1.5,
		min_count	= 1,
		max_count	= 1,  
		offset_x	= 2,		
		entity 	= "data/entities/buildings/arrowtrap_right.xml"
	},
```

*   **Explanation:** This entry defines a unique element, an "arrowtrap_right". It has a relatively high probability (`prob = 1.5`) of spawning, and exactly one instance (`min_count = 1`, `max_count = 1`) will be placed. The `offset_x = 2` suggests it might be positioned slightly to the right of a default point.

**3. Environmental Visual Element Definition:**

```lua
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/beam_01.png",
		visual_file		= "data/biome_impl/crypt/beam_01_visual.png",
		background_file	= "",
		is_unique		= 0
	},
```

*   **Explanation:** This entry defines a visual element, likely a "beam" effect. It has a 100% chance (`prob = 1.0`) of being considered for spawning. It uses specific material and visual files (`.png` images) to render the effect. `is_unique = 0` indicates it's not a one-off element.

## Reference

This file contains 1275 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/crypt.lua).

---