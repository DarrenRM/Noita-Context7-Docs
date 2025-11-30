---
title: Lava Lake Biome Script
category: scripts/
---

# Lava Lake Biome Script

This script defines the behavior and entity spawning for the Lava Lake biome in Noita. It registers specific functions to be called during biome initialization and entity spawning.

## Core Biome Functions

These are the primary functions called by the game's director system for this biome.

### `init(x, y, w, h)`

This function is called when the biome is initialized. In this specific script, it's a placeholder and doesn't contain any custom logic.

### `spawn_music_trigger(x, y)`

Loads a music trigger entity specific to the Lava Lake biome.

```lua
function spawn_music_trigger( x, y )
	EntityLoad( "data/entities/buildings/music_trigger_lavalake.xml", x, y )
end
```

### `spawn_corpse(x, y)`

Spawns various corpse-related props and a book entity, contributing to the biome's atmosphere.

```lua
function spawn_corpse( x, y )
	EntityLoad( "data/entities/props/physics_skull_01.xml", x, y-4 )
	EntityLoad( "data/entities/props/physics_bone_01.xml", x+8, y-4 )
	EntityLoad( "data/entities/props/physics_bone_06.xml", x-12, y-4 )
	EntityLoad( "data/entities/items/books/book_corpse.xml", x, y )
end
```

### `spawn_orb(x, y)`

Spawns a specific orb and a book entity. This function is likely called to provide rewards or progression elements within the biome.

```lua
function spawn_orb(x, y)
	EntityLoad( "data/entities/items/orbs/orb_03.xml", x-10, y )
	EntityLoad( "data/entities/items/books/book_03.xml", x + 20, y )
end
```

### `spawn_small_enemies(x, y)`

Spawns a basic enemy type suitable for the Lava Lake biome.

```lua
function spawn_small_enemies( x, y )
	EntityLoad( "data/entities/animals/fireskull.xml", x, y )
end
```

## Registered Spawn Functions

These functions are registered with the game's director system to be called at specific times or under certain conditions.

| Event ID | Function Name       | Description                                     |
| :------- | :------------------ | :---------------------------------------------- |
| `0xffffeedd` | `init`              | Biome initialization.                           |
| `0xffff5a0f` | `spawn_music_trigger` | Spawns the biome-specific music trigger.        |
| `0xffff5b5f` | `spawn_corpse`      | Spawns corpse-related entities.                 |

## Placeholder Functions

The following functions are defined but do not contain any custom logic in this script. They are likely intended for future implementation or are part of a generic biome template.

*   `spawn_big_enemies(x, y)`
*   `spawn_items(x, y)`
*   `spawn_props(x, y)`
*   `spawn_props2(x, y)`
*   `spawn_props3(x, y)`
*   `spawn_lamp(x, y)`
*   `load_pixel_scene(x, y)`
*   `load_pixel_scene2(x, y)`
*   `spawn_unique_enemy(x, y)`
*   `spawn_unique_enemy2(x, y)`
*   `spawn_unique_enemy3(x, y)`
*   `spawn_ghostlamp(x, y)`
*   `spawn_candles(x, y)`
*   `spawn_potions(x, y)`
*   `spawn_wands()`