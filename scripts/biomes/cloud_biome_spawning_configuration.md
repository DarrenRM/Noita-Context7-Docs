---
title: Cloud Biome Spawning Configuration
category: scripts/biomes
---

# Cloud Biome Spawning Configuration

This document details the spawning configurations for entities and items within the cloud biome in Noita, as defined by the `clouds.lua` script. It outlines the probabilities and types of enemies and items that can appear in this environment.

## Global Spawning Variables

*   **`CHEST_LEVEL`**: An integer representing the level of action IDs spawned from chests. Currently set to `1`.

## Enemy Spawning (`g_small_enemies`)

This table defines the probability distribution for various small enemies that can spawn in the cloud biome. The `prob` attribute determines the likelihood of an entity spawning, while `min_count` and `max_count` define the range of entities to spawn if the probability check passes. `ngpluslevel` indicates the New Game+ level at which the entity becomes available.

| Entity Path                                     | Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | New Game+ Level (`ngpluslevel`) | Notes                                     |
| :---------------------------------------------- | :------------------- | :---------------------- | :---------------------- | :------------------------------ | :---------------------------------------- |
| `data/entities/animals/wraith.xml`              | 0.1                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wraith_glowing.xml`      | 0.3                  | 1                       | 4                       | -                               |                                           |
| `data/entities/animals/wraith_storm.xml`        | 0.3                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/thundermage.xml`         | 0.5                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/thundermage_big.xml`     | 0.05                 | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wizard_tele.xml`         | 0.5                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wizard_swapper.xml`      | 0.4                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/skycrystal_physics.xml`  | 0.5                  | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/spearbot.xml`            | 0.07                 | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wizard_neutral.xml`      | 0.07                 | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wizard_weaken.xml`       | 0.07                 | 1                       | 1                       | -                               |                                           |
| `data/entities/animals/wizard_homing.xml`       | 0.1                  | 1                       | 1                       | 1                               |                                           |
| `data/entities/animals/wizard_hearty.xml`       | 0.1                  | 1                       | 1                       | 2                               |                                           |
| `data/entities/animals/ethereal_being.xml`      | 0.05                 | 1                       | 1                       | 1                               |                                           |
| `data/entities/animals/weakspirit.xml`          | 0.05                 | 1                       | 1                       | 2                               |                                           |

*   **Note:** An initial entry with `prob = 0.5`, `min_count = 0`, `max_count = 0`, and an empty `entity` string indicates a base probability for no spawns.

## Item Spawning (`g_items`)

This table defines the probability distribution for items that can spawn in the cloud biome.

| Entity Path                         | Probability (`prob`) | Min Count (`min_count`) | Max Count (`max_count`) | Notes                               |
| :---------------------------------- | :------------------- | :---------------------- | :---------------------- | :---------------------------------- |
| `data/entities/items/wand_level_03.xml` | 5                    | 1                       | 1                       |                                     |
| `data/entities/items/wand_level_04.xml` | 3                    | 1                       | 1                       |                                     |
| `data/entities/items/wand_level_05.xml` | 1                    | 1                       | 1                       |                                     |

*   **Note:** Similar to enemies, an initial entry with zero counts and probability signifies a baseline for no item spawns.

## Biome-Specific Functions

The following functions are defined but may not be actively used or are placeholders for specific biome generation logic.

*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `spawn_lamp( x, y )`
*   `load_pixel_scene( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`

### `spawn_items(x, y)`

This function is a specialized version for spawning items, particularly in the context of coal mines. It uses a procedural random number generator based on coordinates to potentially load a pixel scene.

```lua
function spawn_items(x, y)
	local r = ProceduralRandom( x-11.631, y+10.2257 )
	
	if (r < 0.45) then
		--LoadPixelScene( "data/biome_impl/wand_altar.png", "data/biome_impl/wand_altar_visual.png", x-15, y-17, "", true )
	end
end
```

### `spawn_small_enemies(x, y)`

This function is called to spawn small enemies according to the `g_small_enemies` configuration.

```lua
function spawn_small_enemies(x, y)
	spawn(g_small_enemies,x,y)
end
```

### `spawn_big_enemies(x, y)`

This function is defined but currently has no implementation, meaning no big enemies are spawned by default in this configuration.

```lua
function spawn_big_enemies(x, y)
end
```

### `load_pixel_scene( x, y )`

This function is intended for loading pixel scenes, but the current implementation is commented out.

```lua
function load_pixel_scene( x, y )
	--spawn(g_cranes,x+35,y+35,0,0)
end
```