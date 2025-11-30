---
title: New Game Plus Biome Map Generation
category: biome
---

# New Game Plus Biome Map Generation

This file defines the logic for generating the biome map for New Game Plus (NG+) runs in Noita. It dynamically alters biome placement and colors based on the `NEW_GAME_PLUS_COUNT` session variable, introducing variety and challenge with each subsequent NG+ cycle.

## Core Functionality

The script's primary purpose is to define and manipulate the `BiomeMap` which dictates the visual appearance and underlying biome types of the game world.

### Key Functions

*   **`paint_biome_area(x, y, w, h, biome_color, buffer)`**: Fills a rectangular area with a specified biome color, with an optional random buffer for smoother edges.
*   **`paint_biome_area_split(x, y, w, h, biome_color1, biome_color2, buffer)`**: Fills a rectangular area with two biome colors, creating a split or gradient effect.
*   **`paint_replace_color(pos_x, pos_y, new_biome_color)`**: Replaces all instances of a specific biome color at a given position with a new biome color.
*   **`paint_cave(x, y, dir, biome_color, length)`**: Generates a winding cave-like structure with a specified biome color, direction, and length.
*   **`shuffleTable(t)`**: Randomly shuffles the elements of a given table.

## Biome Definitions and Color Mapping

The script defines various biome colors using ARGB hexadecimal format. These colors are then assigned to specific biome types. The colors can change based on the NG+ count.

### Default Biome Colors (ARGB)

| Biome Name          | Color      |
| :------------------ | :--------- |
| `biome_coalmines`   | `0xFFD56517` |
| `biome_collapsedmines` | `0xFFD56517` |
| `biome_fungicave`   | `0xFFE861F0` |
| `biome_excavationsite` | `0xFF124445` |
| `biome_snowcaves`   | `0xFF1775D5` |
| `biome_hiisibase`   | `0xFF0046FF` |
| `biome_jungle_1`    | `0xFFA08400` |
| `biome_jungle_2`    | `0xFF808000` |
| `biome_vault`       | `0xFF008000` |
| `biome_sandcaves`   | `0xFFE1CD32` |
| `biomes_snowvault`  | `0xFF0080A8` |
| `biome_wandcave`    | `0xFF006C42` |
| `biome_crypt`       | `0xFF786C42` |

### NG+ Specific Color Variations

The `newgame_n` variable (derived from `SessionNumbersGetValue("NEW_GAME_PLUS_COUNT")`) influences biome colors. For even `newgame_n` values, a distinct set of darker, more muted colors is applied.

```lua
local newgame_n = tonumber( SessionNumbersGetValue("NEW_GAME_PLUS_COUNT") )

if( newgame_n % 2 == 0 ) then
	biome_coalmines = 0xFF3D3E37
	biome_collapsedmines = 0xFF3D3E37
	biome_fungicave = 0xFF3D3E3B
	biome_excavationsite = 0xFF3D3E38
	biome_snowcaves = 0xFF3D3E39
	biome_hiisibase = 0xFF3D3E3A
	biome_jungle_1 = 0xFF3D3E3C
	biome_jungle_2 = 0xFF3D3E3C
	biome_vault = 0xFF3D3E3D
	biome_crypt = 0xFF3D3E3E
end
```

## Biome Randomization and Placement

The script employs several methods to randomize biome placement and types:

### Biome Shuffling

For NG+ counts divisible by 3, the script shuffles a list of all defined biomes and assigns them to specific biome variables, ensuring a different biome layout each time.

```lua
if( newgame_n % 3 == 0 ) then
	all_biomes = {
		0xFFD56517, 0xFFD56517, 0xFFE861F0, 0xFF124445, 0xFF1775D5,
		0xFF0046FF, 0xFFA08400, 0xFF808000, 0xFF008000, 0xFFE1CD32,
		0xFF0080A8, 0xFF006C42, 0xFF786C42,
	}
	shuffleTable( all_biomes )
	-- ... assignment of shuffled biomes ...
end
```

### Biome Swapping

With a 35% chance, adjacent biome types can be swapped, further diversifying the map.

```lua
if( Random( 0, 100 ) < 35 ) then
	biome_coalmines, biome_collapsedmines = biome_collapsedmines, biome_coalmines
end
-- ... other biome swaps ...
```

### Cave Generation

The `paint_cave` function is used to generate various cave systems (fungicave, wandcave, sandcaves) at specific locations with random lengths and directions.

```lua
if( Random( 0, 100 ) < 65 ) then paint_cave( 27, 15, -1, biome_fungicave, Random( 4, 50 ) ) end
-- ... other paint_cave calls ...
```

### Specific Biome Area Painting

The script then proceeds to paint distinct biome areas using `paint_biome_area` and `paint_biome_area_split` at predefined coordinates, applying the potentially randomized biome colors.

```lua
-- biome 1
paint_biome_area( 32, 14, 3, 2,  biome_coalmines, 0 )
paint_biome_area( 28, 15, 4, 1,  biome_collapsedmines, 1 )
-- ... other biome painting ...
```

## Special Features and Decorations

### Wall Painting

If `newgame_n` is divisible by 5, decorative walls are painted using `0xFF3D3D3D`.

```lua
local do_walls = false
if( newgame_n % 5 == 0 ) then
	do_walls = true
end
if( do_walls ) then
	-- ... paint_biome_area calls for walls ...
end
```

### Surface Color Changes

The surface color can be altered based on `newgame_n` divisible by 7, cycling through three different surface colors.

```lua
if( newgame_n % 7 == 0 ) then
	local temp = ( newgame_n / 7 ) % 3
	if( temp == 0 ) then
		paint_replace_color( 16, 5, 0xFFCC9944 ) -- Example color
	-- ... other surface color changes ...
	end
end
```

### Orb Placement

The script defines specific colors for various orbs and places them at randomized locations within the biome map. The `orb_list` table stores the coordinates of these orbs.

```lua
local orb_1 = 0xFFFFD105
-- ... other orb definitions ...

-- pyramid at 51,11
local orb_pyramid = 0xFFC88F5F
BiomeMapSetPixel( 51, 11, orb_pyramid )
orb_list[1] = {51,11}
-- ... other orb placements ...

-- Adjust orb coordinates relative to a central point
for i,v in pairs(orb_list) do
	local x2 = v[1] - 32
	local y2 = v[2] - 14
	v[1] = x2
	v[2] = y2
end
```

### Boss Arena and End Room

Specific colors (`color_end_room`, `color_boss_arena`) are used to define the end room and boss arena areas on the biome map.

```lua
local color_end_room = 0xFF50EED7
local color_boss_arena = 0xFF14EED7

BiomeMapSetPixel( 44, 43, color_end_room )
paint_biome_area( 35, 38, 5, 2, color_boss_arena )
```

## Initialization

The script begins by setting the biome map size and loading an initial image. A fixed random seed is applied for reproducibility of the initial map generation before dynamic NG+ modifications.

```lua
BIOME_MAP_WIDTH = 64
BIOME_MAP_HEIGHT = 48

BiomeMapSetSize( BIOME_MAP_WIDTH, BIOME_MAP_HEIGHT )
BiomeMapLoadImage( 0, 0, "data/biome_impl/biome_map_newgame_plus.png" )

SetRandomSeed( 4573, 4621 )
```