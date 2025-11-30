---
title: Lake Deep Biome Configuration
category: biome/
---

# Lake Deep Biome Configuration

This document details the configuration for the "Lake Deep" biome in Noita, focusing on entity spawning rules.

## Core Biome Functionality

The `lake_deep.lua` script registers a primary spawn function (`init`) that is called by the game's director system. It also includes helper functions for spawning various entities within the biome.

```lua
-- default biome functions that get called if we can't find a a specific biome that works for us
CHEST_LEVEL = 0
dofile_once("data/scripts/director_helpers.lua")
dofile_once("data/scripts/biome_scripts.lua")

RegisterSpawnFunction( 0xffffeedd, "init" )
```

## Entity Spawning Tables

The following tables define the probabilities and counts for different types of entities that can spawn within the Lake Deep biome.

### Small Enemies

This table defines the probability distribution for small enemy entities.

| Probability | Min Count | Max Count | Entity Path                               |
| :---------- | :-------- | :-------- | :---------------------------------------- |
| 1.5         | 0         | 0         | "" (No spawn at this probability)         |
| 0.3         | 1         | 5         | `data/entities/animals/fish.xml`          |
| 0.2         | 1         | 3         | `data/entities/animals/fish_large.xml`    |
| 0.1         | 1         | 1         | `data/entities/animals/eel.xml`           |

### Items

This table defines the probability distribution for various item entities. Note that some items have extremely low spawn probabilities.

| Probability | Min Count | Max Count | Entity Path                                     |
| :---------- | :-------- | :-------- | :---------------------------------------------- |
| 1.2         | 0         | 0         | "" (No spawn at this probability)               |
| 0.01        | 1         | 1         | `data/entities/items/grenadelauncher.xml`       |
| 0.1         | 1         | 1         | `data/entities/items/machinegun.xml`            |
| 0.001       | 1         | 1         | `data/entities/items/opgun.xml`                 |
| 0.0001      | 1         | 1         | `data/entities/items/lightninggun.xml`          |
| 0.02        | 1         | 1         | `data/entities/items/rocketlauncher.xml`        |
| 0.1         | 1         | 1         | `data/entities/items/shotgun.xml`               |

### Ghost Lamp

Configuration for spawning ghostly lamps.

| Probability | Min Count | Max Count | Entity Path                                       |
| :---------- | :-------- | :-------- | :------------------------------------------------ |
| 1.0         | 1         | 1         | `data/entities/props/physics_chain_torch_ghostly.xml` |

### Stash

Configuration for potential stash spawns, which can contain hearts.

| Probability | Min Count | Max Count | Entity Path                       |
| :---------- | :-------- | :-------- | :-------------------------------- |
| 0.4         | 1         | 1         | "" (No specific item)             |
| 0.6         | 1         | 1         | `data/entities/items/pickup/heart.xml` |

### Candles

Defines the types and probabilities of candles that can spawn.

| Probability | Min Count | Max Count | Entity Path                         |
| :---------- | :-------- | :-------- | :---------------------------------- |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_1.xml` |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_2.xml` |
| 0.33        | 1         | 1         | `data/entities/props/physics_candle_3.xml` |

### Lamp

Configuration for spawning a mining lamp.

| Probability | Min Count | Max Count | Entity Path                         |
| :---------- | :-------- | :-------- | :---------------------------------- |
| 0.7         | 1         | 1         | `data/entities/props/physics_mining_lamp.xml` |

## Spawn Functions

These functions are called by the game's director to populate the biome.

### `init(x, y, w, h)`

The main initialization function for the biome. It triggers a parallel check for spawning.

```lua
function init(x, y, w, h)
	parallel_check( x, y )
end
```

### `spawn_small_enemies(x, y)`

Spawns small enemies based on the `g_small_enemies` table.

```lua
function spawn_small_enemies(x, y)
	-- print("spawn_small_enemies")
	if( y < 0 ) then return 0 end
	spawn(g_small_enemies,x,y)
end
```

### `spawn_big_enemies(x, y)`

Placeholder function for spawning big enemies. Currently commented out.

```lua
function spawn_big_enemies(x, y)
	-- print("spawn_small_enemies")
	if( y < 0 ) then return 0 end
	-- spawn(g_big_enemies,x,y)
end
```

### `spawn_items(x, y)`

Placeholder function for spawning items. Currently does nothing.

```lua
function spawn_items(x, y)
	return
end
```

### `spawn_unique_enemy(x, y)`

Placeholder function for spawning unique enemies. Currently does nothing.

```lua
function spawn_unique_enemy(x, y)
end
```

### `spawn_lamp(x, y)`

Placeholder function for spawning lamps. Currently does nothing.

```lua
function spawn_lamp(x, y)
end
```

### `spawn_props(x, y)`

Placeholder function for spawning props. Currently does nothing.

```lua
function spawn_props(x, y)
	return
end
```

### `spawn_potions(x, y)`

Placeholder function for spawning potions. Currently does nothing.

```lua
function spawn_potions( x, y ) end
```