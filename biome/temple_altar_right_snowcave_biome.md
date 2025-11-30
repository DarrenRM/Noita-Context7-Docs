---
title: Temple Altar Right Snowcave Biome
category: biome/
---

# Temple Altar Right Snowcave Biome

This script defines the elements and spawn logic for the "Temple Altar Right Snowcave" biome in Noita. It leverages shared temple assets and custom spawn functions to populate the area.

## Core Functions

This biome primarily uses a set of `RegisterSpawnFunction` calls to associate specific game events or triggers with custom spawning logic.

### Key Spawn Functions

| Function Name        | Description                                                                 |
| :------------------- | :-------------------------------------------------------------------------- |
| `init`               | Initializes the biome, loading its visual and structural components.        |
| `spawn_hp`           | Spawns a full HP pickup, likely for player recovery.                        |
| `spawn_shopitem`     | Spawns a standard shop item.                                                |
| `spawn_cheap_shopitem` | Spawns a cheaper variant of a shop item.                                    |
| `spawn_workshop`     | Spawns a workshop building and a hint for its functionality.                |
| `spawn_workshop_extra` | Spawns an additional workshop building that allows mod integration.         |
| `spawn_motordoor`    | Spawns a temple-themed motor door.                                          |
| `spawn_pressureplate`| Spawns a pressure plate, likely for puzzle or trigger mechanics.            |
| `spawn_lamp`         | Spawns a temple lantern.                                                    |
| `spawn_lamp_long`    | Spawns a longer temple lantern.                                             |
| `spawn_control_workshop` | Spawns a workshop exit building.                                            |
| `spawn_perk_reroll`  | Spawns a perk reroll item.                                                  |
| `spawn_areachecks`   | Spawns various area check entities, likely for level generation logic.      |
| `spawn_rubble`       | Spawns rubble props, adding environmental detail.                           |
| `spawn_statue`       | Spawns a temple statue prop.                                                |

## Loaded Assets and Dependencies

The script relies on several other Lua files for shared functionality and assets.

### `dofile_once` Dependencies

*   `data/scripts/director_helpers.lua`: Contains helper functions for game direction and spawning.
*   `data/scripts/biome_scripts.lua`: General biome-related scripts.
*   `data/scripts/items/generate_shop_item.lua`: Functionality for generating shop items.
*   `data/scripts/biomes/temple_shared.lua`: Shared assets and logic for temple biomes.
*   `data/scripts/perks/perk.lua`: Perk-related definitions.
*   `data/scripts/biomes/temple_altar_top_shared.lua`: Shared assets for the top altar section of temples.

## Key Entity Definitions

The script defines specific configurations for certain entities that can be spawned.

### `g_lamp` Table

This table defines the properties for spawning temple lanterns.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                 | Total probability (likely calculated dynamically). |
| `prob`      | `1.0`                               | Probability for the first entry.          |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `""`                                | Empty entity for the first entry.         |
| `prob`      | `1.0`                               | Probability for the second entry.         |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `"data/entities/props/physics/temple_lantern.xml"` | The actual temple lantern entity.        |

### `g_rubble` Table

This table defines the properties for spawning various rubble props.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                 | Total probability (likely calculated dynamically). |
| `prob`      | `2.0`                               | Probability for the first entry.          |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `""`                                | Empty entity for the first entry.         |
| `prob`      | `0.1`                               | Probability for subsequent entries.       |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `"data/entities/props/physics_temple_rubble_01.xml"` | Rubble entity 1.                          |
| `entity`    | `"data/entities/props/physics_temple_rubble_02.xml"` | Rubble entity 2.                          |
| `entity`    | `"data/entities/props/physics_temple_rubble_03.xml"` | Rubble entity 3.                          |
| `entity`    | `"data/entities/props/physics_temple_rubble_04.xml"` | Rubble entity 4.                          |
| `entity`    | `"data/entities/props/physics_temple_rubble_05.xml"` | Rubble entity 5.                          |
| `entity`    | `"data/entities/props/physics_temple_rubble_06.xml"` | Rubble entity 6.                          |

## Biome Initialization (`init` function)

The `init` function is responsible for setting up the visual and structural elements of the biome.

```lua
function init( x, y, w, h )
	spawn_altar_top(x, y, false) -- Spawns shared altar top elements.

	-- Loads the primary visual and structural layers of the altar.
	LoadPixelScene( "data/biome_impl/temple/altar_right.png", "data/biome_impl/temple/altar_right_visual.png", x, y-40+300, "data/biome_impl/temple/altar_right_background.png", true )
	-- Loads additional visual elements for the altar.
	LoadPixelScene( "data/biome_impl/temple/altar_right_extra.png", "", x, y-40+300+282, "", true )
end
```

## Unused/Placeholder Functions

Several functions are defined but appear to be empty or contain commented-out code, indicating they are either placeholders or not currently used in this specific biome configuration.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_all_perks` (contains a print statement indicating it should not be called and commented-out code)