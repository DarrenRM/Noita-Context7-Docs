---
title: Temple Altar Right (Empty) Biome Script
category: scripts/biomes
---

# Temple Altar Right (Empty) Biome Script

This script defines the behavior and content for an empty "Temple Altar Right" biome in Noita. It primarily focuses on loading visual assets and registering spawn functions for various game elements.

## Core Functionality

This script acts as a template or fallback biome, utilizing default functions and registering specific spawn points for entities.

### Key Spawn Functions Registered

The script registers several functions to be called at specific points during biome generation, triggered by unique hexadecimal IDs.

| ID       | Function Name        | Description                                    |
| :------- | :------------------- | :--------------------------------------------- |
| `0xffffeedd` | `init`               | Initializes the biome, loads visuals.          |
| `0xff6d934c` | `spawn_hp`           | Placeholder for HP spawning.                   |
| `0xff33934c` | `spawn_shopitem`     | Placeholder for shop item spawning.            |
| `0xff33935F` | `spawn_cheap_shopitem` | Placeholder for cheap shop item spawning.      |
| `0xff10822d` | `spawn_workshop`     | Placeholder for workshop item spawning.        |
| `0xff5a822d` | `spawn_workshop_extra` | Placeholder for extra workshop item spawning.  |
| `0xffFAABBA` | `spawn_motordoor`    | Placeholder for motor door spawning.           |
| `0xffFAABBB` | `spawn_pressureplate`| Placeholder for pressure plate spawning.       |
| `0xffA85454` | `spawn_control_workshop`| Placeholder for control workshop spawning.     |
| `0xff03DEAD` | `spawn_areachecks`   | Placeholder for area check functions.          |
| `0xff7345DF` | `spawn_perk_reroll`  | Spawns a perk reroll item.                     |
| `0xffc128ff` | `spawn_rubble`       | Spawns rubble props.                           |
| `0xffa7a707` | `spawn_lamp_long`    | Spawns a long temple lamp.                     |
| `0xff9f2a00` | `spawn_statue`       | Spawns a temple statue.                        |

## Visual Loading (`init` function)

The `init` function is responsible for loading the visual elements that define the biome's appearance.

```lua
function init( x, y, w, h )
	temple_random( x, y ) -- Calls a shared temple randomization function

	-- Load background and foreground sprites for the altar area
	LoadBackgroundSprite( "data/biome_impl/temple/wall_background.png", x, y - 30, 35 )
	LoadPixelScene( "data/biome_impl/temple/altar_top.png", "", x, y-40, "", true )
	LoadPixelScene( "data/biome_impl/temple/altar_right.png", "data/biome_impl/temple/altar_right_visual.png", x, y-40+300, "data/biome_impl/temple/altar_right_background.png", true )
	LoadPixelScene( "data/biome_impl/temple/altar_right_extra.png", "", x, y-40+300+282, "", true )
end
```

## Prop Definitions

The script defines two tables for spawning props: `g_lamp` and `g_rubble`.

### `g_lamp` Table

This table defines the probabilities and entities for spawning lamps.

| Attribute   | Value                               | Description                               |
| :---------- | :---------------------------------- | :---------------------------------------- |
| `total_prob`| `0`                                 | Total probability (not actively used here). |
| `prob`      | `1.0`                               | Probability of spawning.                  |
| `min_count` | `1`                                 | Minimum number of entities to spawn.      |
| `max_count` | `1`                                 | Maximum number of entities to spawn.      |
| `entity`    | `""` or `"data/entities/props/physics/temple_lantern.xml"` | The entity to spawn (empty string means no entity). |

### `g_rubble` Table

This table defines the probabilities and entities for spawning various rubble props.

| Attribute   | Value                                       | Description                               |
| :---------- | :------------------------------------------ | :---------------------------------------- |
| `total_prob`| `0`                                         | Total probability (not actively used here). |
| `prob`      | `2.0` or `0.1`                              | Probability of spawning.                  |
| `min_count` | `1`                                         | Minimum number of entities to spawn.      |
| `max_count` | `1`                                         | Maximum number of entities to spawn.      |
| `entity`    | `""` or specific rubble `.xml` file paths | The entity to spawn.                      |

## Placeholder Spawn Functions

Many of the registered spawn functions are empty, indicating they are intended to be filled in by other scripts or are not actively used in this specific biome configuration.

```lua
-- Placeholder functions for various spawn types
function spawn_small_enemies( x, y ) end
function spawn_big_enemies( x, y ) end
function spawn_items( x, y ) end
function spawn_props( x, y ) end
function spawn_props2( x, y ) end
function spawn_props3( x, y ) end
function load_pixel_scene( x, y ) end
function load_pixel_scene2( x, y ) end
function spawn_unique_enemy( x, y ) end
function spawn_unique_enemy2( x, y ) end
function spawn_unique_enemy3( x, y ) end
function spawn_ghostlamp( x, y ) end
function spawn_candles( x, y ) end
function spawn_potions( x, y ) end
function spawn_hp( x, y ) end
function spawn_shopitem( x, y ) end
function spawn_cheap_shopitem( x, y ) end
function spawn_workshop( x, y ) end
function spawn_workshop_extra( x, y ) end
function spawn_motordoor( x, y ) end
function spawn_pressureplate( x, y ) end
function spawn_control_workshop( x, y ) end
function spawn_all_perks( x, y ) end
function spawn_areachecks( x, y ) end
```

## Specific Spawn Implementations

Some spawn functions have specific implementations.

### `spawn_perk_reroll`

This function directly loads the perk reroll item entity.

```lua
function spawn_perk_reroll( x, y )
	EntityLoad( "data/entities/items/pickup/perk_reroll.xml", x, y )
end
```

### `spawn_rubble`

This function uses the `g_rubble` table to spawn rubble props.

```lua
function spawn_rubble(x, y)
	spawn(g_rubble,x,y,5,0)
end
```

### `spawn_statue`

This function loads a specific temple statue entity.

```lua
function spawn_statue( x, y )
	EntityLoad( "data/entities/props/temple_statue_02.xml", x , y )
end
```

### `spawn_lamp` and `spawn_lamp_long`

These functions utilize the `g_lamp` table to spawn lamps with slight variations in spawn parameters.

```lua
function spawn_lamp(x, y)
	spawn(g_lamp,x,y,0,10)
end

function spawn_lamp_long(x, y)
	spawn(g_lamp,x,y,0,15)
end
```