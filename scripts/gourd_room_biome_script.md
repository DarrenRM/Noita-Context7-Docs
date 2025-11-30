---
title: Gourd Room Biome Script
category: scripts/
---

# Gourd Room Biome Script

This script defines the entities and behaviors for the "Gourd Room" biome in Noita. It handles the spawning of specific items and enemies within this environment.

## Core Functionality

The script registers spawn functions that are called by the game's director system at specific points during level generation.

### Registered Spawn Functions

| Function Name   | Trigger ID | Description                                     |
| :-------------- | :--------- | :---------------------------------------------- |
| `init`          | `0xffffeedd` | Initializes the biome, potentially loading scenes. |
| `spawn_fruit`   | `0xff31d0b0` | Spawns gourds and a shotgunner enemy.           |
| `spawn_book`    | `0xff9dd0b0` | Spawns a music book and physics props.          |

## Key Functions

### `init(x, y, w, h)`

This function is called during the biome's initialization. The current implementation is commented out but suggests the potential to load a pixel scene for the biome's visual layout.

```lua
function init( x, y, w, h )
	--LoadPixelScene( "data/biome_impl/gourd_room.png", "", x, y, "", true )
end
```

### `spawn_fruit(x, y)`

This function is responsible for populating the biome with gourds and a specific enemy.

*   **Gourds:** Multiple `gourd.xml` entities are spawned around the given coordinates.
*   **Shotgunner:** A `shotgunner.xml` entity is spawned at a slightly offset position.

```lua
function spawn_fruit( x, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x - 12, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x + 12, y )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x, y - 12 )
	EntityLoad( "data/entities/items/pickup/gourd.xml", x - 12, y ) -- Duplicate entry, likely intended for variation or error
	EntityLoad( "data/entities/animals/shotgunner.xml", x + 24, y - 24 )
end
```

### `spawn_book(x, y)`

This function spawns a specific book and some physics-based props.

*   **Music Book:** `book_music_c.xml` is spawned.
*   **Physics Props:** `physics_skull_01.xml` and `physics_bone_02.xml` are spawned at relative positions.

```lua
function spawn_book( x, y )
	EntityLoad( "data/entities/items/books/book_music_c.xml", x, y )
	EntityLoad( "data/entities/props/physics_skull_01.xml", x + 8, y )
	EntityLoad( "data/entities/props/physics_bone_02.xml", x + 12, y - 16 )
end
```

### `spawn_lamp(x, y)`

This function handles the spawning of lamps within the biome. It uses a probability table `g_lamp` to determine which lamp to spawn.

#### `g_lamp` Table

This table defines the possible lamps to spawn and their probabilities.

| Attribute   | Value                                  | Description                                     |
| :---------- | :------------------------------------- | :---------------------------------------------- |
| `total_prob`| `0`                                    | Total probability (currently unused/zero).      |
| `prob`      | `1.0`                                  | Probability of spawning this entry.             |
| `min_count` | `1`                                    | Minimum number of entities to spawn.            |
| `max_count` | `1`                                    | Maximum number of entities to spawn.            |
| `entity`    | `"data/entities/props/physics/lantern_small.xml"` | The entity to spawn (a small lantern). |

```lua
g_lamp =
{
	total_prob = 0,
	-- add skullflys after this step
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,    
		entity 	= "data/entities/props/physics/lantern_small.xml"
	},
}

function spawn_lamp(x, y)
	spawn(g_lamp,x,y,0,0)
end
```

## Unused/Placeholder Functions

The following functions are defined but do not contain any implementation, indicating they are either placeholders for future development or not used in this specific biome script.

*   `spawn_small_enemies( x, y )`
*   `spawn_big_enemies( x, y )`
*   `spawn_items( x, y )`
*   `spawn_props( x, y )`
*   `spawn_props2( x, y )`
*   `spawn_props3( x, y )`
*   `load_pixel_scene2( x, y )`
*   `spawn_unique_enemy( x, y )`
*   `spawn_unique_enemy2( x, y )`
*   `spawn_unique_enemy3( x, y )`
*   `spawn_ghostlamp( x, y )`
*   `spawn_candles( x, y )`
*   `spawn_potions( x, y )`
*   `spawn_wands( x, y )`
*   `spawn_orb(x, y)`