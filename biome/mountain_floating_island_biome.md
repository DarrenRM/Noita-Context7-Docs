---
title: Mountain Floating Island Biome
category: biome
---

# Mountain Floating Island Biome

This document describes the configuration for the "Mountain Floating Island" biome in Noita, intended for AI-assisted modding.

## Core Biome Configuration

This biome is registered to be loaded under specific conditions, indicated by the `RegisterSpawnFunction` calls.

### Spawn Functions

| Event ID | Function Name     | Description                                                              |
| :------- | :---------------- | :----------------------------------------------------------------------- |
| `0xffffeedd` | `init`            | Initializes the biome, loading its visual and pixel data.                |
| `0xffffd1a1` | `spawn_sampo_spot` | Spawns a specific "sampo spot" entity, likely a unique encounter. |

## Initialization (`init`)

The `init` function is responsible for loading the visual and structural data of the floating island biome.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/mountain/floating_island.png", "data/biome_impl/mountain/floating_island_visual.png", x, y, "", true )
end
```

*   **`x`, `y`, `w`, `h`**: These parameters define the position and dimensions of the biome area.
*   **`LoadPixelScene`**: This function loads the biome's geometry and visual appearance.
    *   `"data/biome_impl/mountain/floating_island.png"`: The pixel data defining the biome's structure.
    *   `"data/biome_impl/mountain/floating_island_visual.png"`: The visual layer for the biome.
    *   `x`, `y`: The world coordinates where the biome is placed.
    *   `""`: An empty string, likely for optional biome-specific configurations not used here.
    *   `true`: A boolean flag, potentially indicating whether to use this biome's specific loading logic.

## Entity Spawning

This biome includes functions for spawning specific entities.

### `spawn_orb`

This function is not directly registered as a spawn function but is defined within the script, suggesting it might be called by other game systems or for specific events. It spawns a random orb and a book.

```lua
function spawn_orb(x, y)
	EntityLoad( "data/entities/items/orbs/orb_00.xml", x, y )
	EntityLoad( "data/entities/items/books/book_00.xml", x+18, y )
end
```

*   **`x`, `y`**: The world coordinates for spawning.
*   **`EntityLoad`**: Loads an entity from its XML definition.
    *   `"data/entities/items/orbs/orb_00.xml"`: Loads a generic orb.
    *   `"data/entities/items/books/book_00.xml"`: Loads a generic book, offset slightly from the orb.

### `spawn_sampo_spot`

This function is registered to be called when the `0xffffd1a1` event occurs, spawning a unique "sampo spot" entity.

```lua
function spawn_sampo_spot(x, y)
	EntityLoad( "data/entities/animals/boss_centipede/ending/ending_sampo_spot_mountain.xml", x, y )
end
```

*   **`x`, `y`**: The world coordinates for spawning.
*   **`EntityLoad`**: Loads the specific "sampo spot" entity.
    *   `"data/entities/animals/boss_centipede/ending/ending_sampo_spot_mountain.xml"`: The XML definition for this unique entity.

## Dependencies

This script relies on external Lua files for core functionalities.

*   `dofile_once("data/scripts/director_helpers.lua")`: Provides helper functions for game direction and event management.
*   `dofile_once("data/scripts/biomes/mountain/mountain.lua")`: Likely contains base configurations or functions for mountain biomes.