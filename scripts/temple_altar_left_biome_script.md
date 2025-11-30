---
title: Temple Altar Left Biome Script
category: scripts
---

# Temple Altar Left Biome Script

This script defines the behavior and entity spawning for the "Temple Altar Left" biome in Noita. It handles the initialization of the biome, the loading of its visual assets, and the conditional spawning of various entities based on specific game states or random chance.

## Core Functionality

The script primarily uses `RegisterSpawnFunction` to associate specific entity IDs (represented by hexadecimal values) with Lua functions that will be called when those entities are encountered during level generation.

### Key Spawn Functions:

*   **`init(x, y, w, h)`**: This is the main initialization function for the biome. It calls `spawn_altar_top` to set up the altar structure and then loads the biome's visual and background assets using `LoadPixelScene`.
*   **`spawn_hp(x, y)`**: Spawns health pickups (full HP and refresh hearts) at the given coordinates.
*   **`spawn_shopitem(x, y)`**: Spawns a regular shop item using the `generate_shop_item` helper function.
*   **`spawn_cheap_shopitem(x, y)`**: Spawns a cheaper shop item, also using `generate_shop_item`.
*   **`spawn_workshop(x, y)`**: Places a standard workshop building.
*   **`spawn_workshop_extra(x, y)`**: Places a workshop building that allows mods.
*   **`spawn_motordoor(x, y)`**: Spawns a temple-themed motor door.
*   **`spawn_pressureplate(x, y)`**: Places a temple pressure plate.
*   **`spawn_lamp(x, y)` / `spawn_lamp_long(x, y)`**: Spawns temple lanterns with varying lengths.
*   **`spawn_music_trigger(x, y)`**: Intended to spawn a music trigger, though the entity loading is commented out.
*   **`spawn_duplicator(x, y)`**: Places a temple duplicator building.
*   **`spawn_areachecks(x, y)`**: Spawns various "area check" entities, which are likely used by the game to define playable zones or trigger events within the biome. This function includes a conditional check (`temple_should_we_spawn_checkers`) before spawning.
*   **`spawn_rubble(x, y)`**: Spawns rubble props with a defined probability distribution.
*   **`spawn_vines(x, y)`**: Spawns vine entities, with different lengths and probabilities.
*   **`spawn_statue(x, y)`**: Spawns a temple statue. It conditionally spawns a "greed crystal" and a green statue if the `greed_curse` flag is active.
*   **`spawn_fish(x, y)`**: Spawns fish entities. The number of fish spawned is determined by the player's total orb count.

## Entity Spawning Tables

The script defines several tables that dictate the entities to be spawned and their associated probabilities and counts.

### `g_lamp` Table

Controls the spawning of temple lanterns.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `total_prob`| Total probability (calculated internally).       |
| `prob`      | Probability of this specific entry being chosen. |
| `min_count` | Minimum number of entities to spawn.             |
| `max_count` | Maximum number of entities to spawn.             |
| `entity`    | Path to the entity XML file.                     |

*   **Entry 1**: `prob = 1.0`, `entity = ""` (likely a placeholder or no spawn).
*   **Entry 2**: `prob = 1.0`, `entity = "data/entities/props/physics/temple_lantern.xml"`.

### `g_fish` Table

Controls the spawning of fish entities.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `total_prob`| Total probability (calculated internally).       |
| `prob`      | Probability of this specific entry being chosen. |
| `min_count` | Minimum number of entities to spawn.             |
| `max_count` | Maximum number of entities to spawn.             |
| `entity`    | Path to the entity XML file.                     |

*   **Entry 1**: `prob = 1.0`, `entity = "data/entities/animals/fish.xml"`.
*   **Entry 2**: `prob = 1.0`, `entity = ""` (likely a placeholder or no spawn).

### `g_rubble` Table

Controls the spawning of various rubble props.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `total_prob`| Total probability (calculated internally).       |
| `prob`      | Probability of this specific entry being chosen. |
| `min_count` | Minimum number of entities to spawn.             |
| `max_count` | Maximum number of entities to spawn.             |
| `entity`    | Path to the entity XML file.                     |

*   **Entry 1**: `prob = 2.0`, `entity = ""` (likely a placeholder or no spawn).
*   **Entries 2-7**: `prob = 0.1`, each spawning a different rubble prop (`physics_temple_rubble_01.xml` to `_06.xml`).

### `g_vines` Table

Controls the spawning of vine entities with different lengths.

| Attribute   | Description                                      |
| :---------- | :----------------------------------------------- |
| `total_prob`| Total probability (calculated internally).       |
| `prob`      | Probability of this specific entry being chosen. |
| `min_count` | Minimum number of entities to spawn.             |
| `max_count` | Maximum number of entities to spawn.             |
| `entity`    | Path to the entity XML file.                     |

*   **Entry 1**: `prob = 0.5`, `entity = ""` (likely a placeholder or no spawn).
*   **Entry 2**: `prob = 0.4`, `entity = "data/entities/verlet_chains/vines/verlet_vine.xml"`.
*   **Entry 3**: `prob = 0.3`, `entity = "data/entities/verlet_chains/vines/verlet_vine_long.xml"`.
*   **Entry 4**: `prob = 0.2`, `entity = "data/entities/verlet_chains/vines/verlet_vine_short.xml"`.
*   **Entry 5**: `prob = 0.2`, `entity = "data/entities/verlet_chains/vines/verlet_vine_shorter.xml"`.

## Helper Functions

The script includes several empty or placeholder functions that are likely intended for future implementation or are part of a broader biome system.

*   `spawn_small_enemies(x, y)`
*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`

## Dependencies

This script relies on several other Lua files for its functionality:

*   `data/scripts/director_helpers.lua`
*   `data/scripts/biome_scripts.lua`
*   `data/scripts/items/generate_shop_item.lua`
*   `data/scripts/biomes/temple_shared.lua`
*   `data/scripts/biomes/temple_altar_top_shared.lua`