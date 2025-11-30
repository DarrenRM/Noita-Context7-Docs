---
title: Boss Arena Biome Script
category: scripts/biomes
---

# Boss Arena Biome Script

This script defines the entities and behaviors associated with the boss arena biome in Noita. It handles the spawning of various elements, including items, props, enemies, and special structures, to create a challenging and unique encounter environment.

## Core Functionality

The script primarily registers and defines functions for spawning specific entities at designated locations within the boss arena. These functions are triggered by the game's biome generation system.

## Key Spawn Functions

This section highlights the most important functions responsible for populating the boss arena.

### `spawn_hp(x, y)`

Spawns essential healing and utility items for the player.

*   **`data/entities/items/pickup/heart_fullhp_temple.xml`**: A full HP restore pickup.
*   **`data/entities/buildings/music_trigger_temple.xml`**: Triggers specific music for the arena.
*   **`data/entities/items/pickup/spell_refresh.xml`**: Refreshes player's spells.
*   **`data/entities/buildings/coop_respawn.xml`**: A respawn point for cooperative play.

### `spawn_all_shopitems(x, y)`

Handles the generation of shop items and potentially wands within the arena.

*   Uses `temple_random` to determine if shop items or perks should spawn.
*   Spawns a `shop_hitbox`.
*   Generates a configurable number of shop items (`TEMPLE_SHOP_ITEM_COUNT` global variable).
*   Can spawn either regular shop items or wands, with a chance for a "sale" item.
*   Includes visual elements for the shop rows using `LoadPixelScene`.

### `spawn_boss_music_and_statues(x, y)`

Sets up the visual and auditory atmosphere for the boss fight.

*   **`data/entities/props/boss_arena_statue_*.xml`**: Spawns decorative statues.
*   **`data/entities/animals/boss_centipede/boss_music_buildup_trigger.xml`**: Initiates the boss encounter music.

### `spawn_items(x, y)`

Spawns the primary boss entity and related items.

*   **`data/entities/animals/boss_centipede/boss_centipede.xml`**: The main boss entity.
*   **`data/entities/animals/boss_centipede/sampo.xml`**: A special item that spawns only if the game is not completed.
*   **`data/entities/animals/boss_centipede/reference_point.xml`**: A reference point for the boss.

### `spawn_rubble(x, y)`

Adds environmental detail with destructible rubble.

*   Utilizes the `g_rubble` table to spawn various rubble entities.

### `spawn_vines(x, y)`

Introduces dynamic vine elements to the arena.

*   Uses the `g_vines` table to spawn different lengths and types of vines.

## Registered Spawn Functions

The following table lists the registered spawn functions and their associated hexadecimal color codes, which are used by the game to identify and trigger these functions during biome generation.

| Hex Color Code | Function Name                 | Description                                      |
| :------------- | :---------------------------- | :----------------------------------------------- |
| `0xff6d934c`   | `spawn_hp`                    | Spawns healing and utility items.                |
| `0xff33934c`   | `spawn_all_shopitems`         | Spawns shop items and wands.                     |
| `0xff10822d`   | `spawn_workshop`              | Spawns a standard workshop.                      |
| `0xff5a822d`   | `spawn_workshop_extra`        | Spawns a workshop that allows mods.              |
| `0xffFAABBA`   | `spawn_motordoor`             | Spawns a temple motor door.                      |
| `0xffFAABBB`   | `spawn_pressureplate`         | Spawns a temple pressure plate.                  |
| `0xff03DEAD`   | `spawn_areachecks_left`       | Spawns area check entities on the left side.     |
| `0xffDEDEAD`   | `spawn_areachecks_right`      | Spawns area check entities on the right side.    |
| `0xffA85454`   | `spawn_control_workshop`      | Spawns a workshop exit.                          |
| `0xff845454`   | `spawn_boss_music_and_statues`| Spawns boss statues and music triggers.          |
| `0xff784dd2`   | `spawn_worm_deflector`        | Spawns a worm deflector.                         |
| `0xff7345DF`   | `spawn_perk_reroll`           | Spawns a perk reroll item.                       |
| `0xffc128ff`   | `spawn_rubble`                | Spawns rubble props.                             |
| `0xffa7a707`   | `spawn_lamp_long`             | Spawns a long temple lamp.                       |
| `0xff80FF5A`   | `spawn_vines`                 | Spawns vine entities.                            |
| `0xff03fade`   | `spawn_aabb`                  | Spawns an AABB entity (likely for collision).    |
| `0xffffb870`   | `spawn_spell_visualizer`      | Spawns a spell visualizer and AABB.              |

## Entity Definitions

The script defines several tables that dictate the properties and entities to be spawned for specific environmental elements.

### `g_lamp`

Defines parameters for spawning lamps.

| Attribute   | Type   | Description                               |
| :---------- | :----- | :---------------------------------------- |
| `total_prob`| Number | Total probability for this group.         |
| `prob`      | Number | Probability of spawning a specific entry. |
| `min_count` | Number | Minimum number of entities to spawn.      |
| `max_count` | Number | Maximum number of entities to spawn.      |
| `entity`    | String | Path to the entity XML file to spawn.     |

### `g_rubble`

Defines parameters for spawning various types of rubble.

| Attribute   | Type   | Description                               |
| :---------- | :----- | :---------------------------------------- |
| `total_prob`| Number | Total probability for this group.         |
| `prob`      | Number | Probability of spawning a specific entry. |
| `min_count` | Number | Minimum number of entities to spawn.      |
| `max_count` | Number | Maximum number of entities to spawn.      |
| `entity`    | String | Path to the entity XML file to spawn.     |

### `g_vines`

Defines parameters for spawning different vine configurations.

| Attribute   | Type   | Description                               |
| :---------- | :----- | :---------------------------------------- |
| `total_prob`| Number | Total probability for this group.         |
| `prob`      | Number | Probability of spawning a specific entry. |
| `min_count` | Number | Minimum number of entities to spawn.      |
| `max_count` | Number | Maximum number of entities to spawn.      |
| `entity`    | String | Path to the entity XML file to spawn.     |

## Helper Functions

The script relies on several external Lua files for shared functionality.

*   `data/scripts/director_helpers.lua`: Contains general helper functions for game direction and spawning.
*   `data/scripts/biome_scripts.lua`: Provides functions related to biome-specific behaviors.
*   `data/scripts/items/generate_shop_item.lua`: Used for dynamically generating shop items.
*   `data/scripts/lib/utilities.lua`: Contains various utility functions.
*   `data/scripts/biomes/temple_shared.lua`: Shared functions and definitions for temple biomes.
*   `data/scripts/perks/perk.lua`: Defines perk-related logic.

## Modding Considerations

*   **Entity Replacement**: To change the boss or its associated items, modify the `EntityLoad` calls within the relevant `spawn_` functions.
*   **Shop Customization**: Adjust the `TEMPLE_SHOP_ITEM_COUNT` global variable or modify the logic within `spawn_all_shopitems` to alter shop contents and behavior.
*   **Environmental Elements**: The `g_lamp`, `g_rubble`, and `g_vines` tables can be extended or modified to include new props or change their spawn probabilities.
*   **Spawn Function Registration**: New spawn functions can be registered using `RegisterSpawnFunction` with a unique hexadecimal color code. Ensure these functions are defined within this script or included via `dofile`.
*   **Conditional Spawning**: Observe the use of `GameHasFlagRun` and other conditional checks for spawning specific entities (e.g., `sampo.xml`). These can be leveraged for more complex modding scenarios.