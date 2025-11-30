---
title: vault
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/vault.lua
---

# vault

This `vault.lua` file is a crucial part of Noita's game generation system, specifically defining the entities and structures that can appear within the "Vault" biome. Biomes in Noita are distinct areas with unique visual themes, enemy types, and environmental hazards. This file dictates the composition of the Vault, influencing gameplay by determining what players will encounter in terms of enemies, props, and interactive elements. It acts as a blueprint for populating this specific area of the game world.

## File Structure

The `vault.lua` file is structured as a Lua script. It primarily uses Lua tables to define various categories of game entities and their spawn probabilities. The core pattern involves defining global tables (e.g., `g_small_enemies`, `g_props`) that contain lists of potential entities to spawn.

Each entry within these tables typically follows a consistent format:

*   **`prob`**: A floating-point number representing the probability of this specific entity or group of entities being chosen for spawning. Higher values mean a greater chance.
*   **`min_count`**: The minimum number of instances of the entity to spawn if it's selected.
*   **`max_count`**: The maximum number of instances of the entity to spawn if it's selected.
*   **`entity`**: A string representing the file path to the entity's XML definition. This is the most common way to specify a single entity.
*   **`entities`**: An array (Lua table) of strings, where each string is a file path to an entity's XML definition. This is used when multiple entities can be chosen from a group, often with an implicit equal probability among them.
*   **`offset_y`**: (Observed in `g_props`) An integer that can adjust the vertical offset of the spawned entity.

The file also includes calls to `RegisterSpawnFunction`, which associate specific hexadecimal IDs with functions that handle the spawning of various game elements like pixel scenes, turrets, pipes, and traps. These functions likely manage the placement and instantiation of these elements within the game world.

## Key Patterns

*   **Categorization of Spawns**: The file is organized into distinct tables for different types of game elements, such as `g_small_enemies`, `g_props`, `g_hanging_props`, and `g_apparatus`. This allows for a clear separation of concerns and makes it easier to manage the spawning logic for each category.
*   **Probabilistic Spawning**: The use of `prob`, `min_count`, and `max_count` indicates a system where the game randomly selects entities to spawn based on defined probabilities and quantities. This creates variety in each playthrough.
*   **Entity Definitions**: Entities are referenced by their file paths (e.g., `"data/entities/animals/vault/drone_physics.xml"`), implying that the actual definitions of these entities reside in separate XML files.
*   **Fallback/Empty Entries**: Some entries, particularly at the beginning of probability lists, have an empty `entity = ""` and a `prob` that contributes to the `total_prob`. This often serves as a "nothing spawns here" or a placeholder that allows the `total_prob` to be calculated correctly, ensuring that the probabilities sum up appropriately for the random selection process.
*   **`total_prob` Calculation**: Each main spawning table includes a `total_prob = 0` entry. The probabilities of individual entries are then added to this, likely for internal game logic to normalize or manage the overall spawn chances.
*   **Helper Functions**: The script begins by `dofile_once`ing several other Lua files (e.g., `director_helpers.lua`, `biome_scripts.lua`). This indicates that `vault.lua` relies on shared utility functions and definitions from other parts of the game's scripting system.

## Sample Entries

**1. `g_small_enemies` Entry:**

```lua
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 2,
		entity 	= "data/entities/animals/vault/drone_physics.xml"
	},
```

This entry defines a potential spawn for small enemies within the Vault. If this entry is randomly selected, the game will attempt to spawn between 1 and 2 instances of the `drone_physics.xml` entity. The `prob = 0.3` indicates a 30% chance for this specific spawn to be considered among the other small enemy options.

**2. `g_props` Entry:**

```lua
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_box_explosive.xml"
	},
```

This entry from the `g_props` table specifies that an explosive physics box (`physics_box_explosive.xml`) has a 30% chance of being spawned, with exactly one instance being placed if chosen. This contributes to the environmental hazards and interactive elements within the Vault.

**3. `g_apparatus` Entry:**

```lua
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/vault_apparatus_01.xml"
	},
```

This entry from the `g_apparatus` table shows a high probability (`prob = 1.0`) for spawning a specific apparatus, `vault_apparatus_01.xml`. This suggests that certain apparatuses are very common or guaranteed to appear in the Vault biome, contributing to its unique visual and functional characteristics.

## Reference

This file contains 1278 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/vault.lua).

---