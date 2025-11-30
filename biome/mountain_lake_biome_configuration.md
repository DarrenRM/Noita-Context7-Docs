---
title: Mountain Lake Biome Configuration
category: biome
---

# Mountain Lake Biome Configuration

This document outlines the configuration for the "Mountain Lake" biome in Noita, focusing on its spawning mechanics and entity distribution.

## Core Biome Settings

*   **`CHEST_LEVEL`**: `3` - Indicates the general difficulty or progression level associated with this biome, influencing chest contents.
*   **`dofile_once`**:
    *   `data/scripts/director_helpers.lua`: Loads essential helper functions for game direction and spawning.
    *   `data/scripts/biomes/mountain/mountain.lua`: Imports base configurations for mountain biomes.

## Spawn Functions

The biome utilizes specific functions registered to be called at certain points during gameplay.

*   **`RegisterSpawnFunction( 0xffffeedd, "init" )`**: Registers the `init` function to be called with a specific identifier. This function is typically responsible for initial biome setup.
*   **`RegisterSpawnFunction( 0xffb4a00a, "spawn_fish" )`**: Registers the `spawn_fish` function to be called with another identifier. This function handles the spawning of fish entities.

## Fish Spawning Configuration (`g_fish`)

This table defines the entities that can spawn as fish within the Mountain Lake biome.

| Attribute   | Description                                                              |
| :---------- | :----------------------------------------------------------------------- |
| `total_prob`| The cumulative probability for all fish entries. (Currently `0`, implying specific probabilities within entries are key). |
| `prob`      | The probability of this specific fish entry spawning.                    |
| `min_count` | The minimum number of this entity to spawn.                              |
| `max_count` | The maximum number of this entity to spawn.                              |
| `entity`    | The path to the entity XML file to spawn.                                |

### Fish Entries:

*   **Entry 1**:
    *   `prob`: `1.0`
    *   `min_count`: `1`
    *   `max_count`: `1`
    *   `entity`: `"data/entities/animals/fish.xml"` - Spawns a standard fish entity.
*   **Entry 2**:
    *   `prob`: `1.0`
    *   `min_count`: `1`
    *   `max_count`: `1`
    *   `entity`: `""` - This entry appears to be a placeholder or an incomplete entry, as it specifies no entity to spawn.

## Biome Initialization (`init`)

The `init` function is called during the biome's setup phase.

```lua
function init( x, y, w, h )
	-- LoadPixelScene( "data/biome_impl/mountain_lake.png", "", x, y, "", true )
	-- LoadPixelScene( "data/biome_impl/mountain_lake_top.png", "", x-88, y, "", true )
end
```

*   The commented-out `LoadPixelScene` calls suggest that this biome would typically load specific pixel scene data for its visual representation. These are currently inactive.

## Fish Spawning (`spawn_fish`)

The `spawn_fish` function is responsible for instantiating fish entities based on the `g_fish` configuration.

```lua
function spawn_fish(x, y)
	spawn(g_fish,x,y)
end
```

*   This function takes coordinates `x` and `y` and calls the generic `spawn` function, passing the `g_fish` table to determine which fish entities to spawn at the given location.