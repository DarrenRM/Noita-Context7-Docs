---
title: snowcastle
category: scripts
source: https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/snowcastle.lua
---

# snowcastle

This file, `snowcastle.lua`, defines the entities and spawn logic for the "Snowcastle" biome in Noita. It acts as a blueprint for what players will encounter in this specific area of the game world, dictating the types of enemies, props, and environmental elements that can appear. By registering spawn functions and defining probability tables for various entity groups, this script directly influences the gameplay experience within the Snowcastle.

## File Structure

The file is primarily structured using Lua's table syntax. It defines global variables, most of which are tables representing different categories of entities or spawnable items. These tables often contain:

*   **`total_prob`**: A variable that seems to accumulate probabilities, though its exact role in the spawning logic isn't fully clear from the samples.
*   **Individual entries within tables**: These entries are themselves tables, defining specific spawnable entities. Key fields within these entries include:
    *   **`prob`**: A probability value that influences the likelihood of this specific entity or group of entities being spawned.
    *   **`min_count`**: The minimum number of entities to spawn.
    *   **`max_count`**: The maximum number of entities to spawn.
    *   **`entity`**: A string representing the path to an XML file defining a single entity.
    *   **`entities`**: A table containing multiple `entity` definitions, allowing for a group of different entities to be spawned with varying counts. This can include nested tables for more complex spawn configurations.
    *   **`spawn_check`**: An optional function that can be executed to determine if the entity should spawn, based on game conditions (e.g., `GameGetDateAndTimeLocal()` for time-based spawning).
    *   **`ngpluslevel`**: An integer indicating that the entity should only spawn in New Game+ modes, with the value representing the minimum NG+ level required.

The file also uses `RegisterSpawnFunction` calls to associate specific hexadecimal color codes (likely representing tile types or regions) with Lua functions that handle spawning.

## Key Patterns

Several patterns are evident in the sampled content:

*   **Categorization of Spawns**: Entities are grouped into logical categories like `g_small_enemies`, `g_big_enemies`, `g_vines`, `g_forcefield_generator`, and `g_pods_large`. This organization makes it easier to manage and modify spawn lists.
*   **Probability-Driven Spawning**: The `prob` field is central to determining what appears. Higher probabilities mean a greater chance of an entity spawning.
*   **Conditional Spawning**: The `spawn_check` function allows for dynamic spawning based on in-game conditions, such as the current date and time.
*   **New Game+ Specific Spawns**: The `ngpluslevel` attribute clearly delineates entities that are intended for later playthroughs, adding difficulty or variety.
*   **Hierarchical Entity Definitions**: The `entities` field can contain nested tables, allowing for complex combinations of entities to be spawned together, each with its own `min_count` and `max_count`.
*   **Default/Fallback Entries**: Many tables include an entry with `entity = ""` and a probability, which likely serves as a "nothing spawns here" or a default fallback.

## Sample Entries

Here are a few representative examples from the sampled content:

1.  **Small Enemy Definition (`g_small_enemies`)**:
    ```lua
    {
        prob   		= 0.1,
        min_count	= 1,
        max_count	= 2,
        entities 	= {
            "data/entities/animals/scavenger_grenade.xml",
            "data/entities/animals/scavenger_smg.xml",
        }
    },
    ```
    This entry defines a group of small enemies. It has a 10% probability (`prob = 0.1`) of spawning between 1 and 2 instances (`min_count = 1`, `max_count = 2`). The `entities` field specifies that either a `scavenger_grenade.xml` or a `scavenger_smg.xml` can spawn.

2.  **Drunk Enemy Group with Time Check (`g_small_enemies` sample)**:
    ```lua
    {
        prob   		= 1.1,
        min_count	= 1,
        max_count	= 1,
        entities 	= {
            {
                min_count	= 0,
                max_count	= 1,
                entity	= "data/entities/animals/drunk/scavenger_grenade.xml",
            },
            {
                min_count	= 1,
                max_count	= 2,
                entity	= "data/entities/animals/drunk/scavenger_smg.xml",
            },
        },
        spawn_check = function()
            local year,month,day,temp1,temp2,temp3,jussi = GameGetDateAndTimeLocal()
            return jussi
        end,
    },
    ```
    This entry demonstrates a more complex spawn. It has a high probability (`prob = 1.1`) and spawns one instance. The `entities` list contains two sub-definitions: one for `drunk/scavenger_grenade.xml` (0-1 count) and another for `drunk/scavenger_smg.xml` (1-2 count). Crucially, it includes a `spawn_check` function that uses `GameGetDateAndTimeLocal()`, implying these "drunk" enemies might only appear at certain times or days.

3.  **New Game+ Specific Enemy (`g_big_enemies` sample)**:
    ```lua
    {
        prob   		= 0.05,
        min_count	= 1,
        max_count	= 1,
        entity 	= "data/entities/animals/necrobot_super.xml",
        ngpluslevel = 3,
    },
    ```
    This entry defines a `necrobot_super.xml` entity. It has a 5% probability (`prob = 0.05`) of spawning one instance (`min_count = 1`, `max_count = 1`). The `ngpluslevel = 3` attribute signifies that this enemy will only appear in New Game+ modes, specifically from level 3 onwards.

## Reference

This file contains 1491 lines. For complete data, see the [full source](https://github.com/NathanSnail/noitadata/tree/main/data/scripts/biomes/snowcastle.lua).

---