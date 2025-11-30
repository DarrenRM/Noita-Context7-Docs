---
title: Temple Altar Top Biome Generation
category: scripts/
---

# Temple Altar Top Biome Generation

This script defines the generation logic for the "Temple Altar Top" biome in Noita. It handles the placement of various visual elements and special variants based on random chance and world depth.

## Core Functionality

The primary function `spawn_altar_top(x, y, is_solid)` is responsible for generating the biome.

### Key Parameters

*   **`x`, `y`**: The coordinates for placing the biome elements.
*   **`is_solid`**: A boolean flag that determines if a solid layer is added.

## Biome Variants

The script introduces several variations of the altar top, primarily determined by random chance using `Random(1, 50)`.

### Visual Scene Loading

The `LoadPixelScene` function is used to load different visual configurations. The `file_visual` variable is consistently set to `"data/biome_impl/temple/altar_top_visual.png"`.

### Variant Probabilities and Descriptions

| Random Value | Scene File                                     | Description                               |
| :----------- | :--------------------------------------------- | :---------------------------------------- |
| 5            | `data/biome_impl/temple/altar_top_water.png`   | Generates a water-themed altar top.       |
| 8            | `data/biome_impl/temple/altar_top_blood.png`   | Generates a blood-themed altar top.       |
| 11           | `data/biome_impl/temple/altar_top_oil.png`     | Generates an oil-themed altar top.        |
| 13           | `data/biome_impl/temple/altar_top_radioactive.png` | Generates a radioactive altar top.        |
| 15           | `data/biome_impl/temple/altar_top_lava.png`    | Generates a lava-themed altar top.        |
| Otherwise    | `data/biome_impl/temple/altar_top.png`         | The default, standard altar top.          |

### Special Case: Boss Arena

If the `y` coordinate is greater than `12000`, the biome will always generate as a boss arena:

*   `data/biome_impl/temple/altar_top_boss_arena.png`

### Solid Layer

If the `is_solid` parameter is `true`, an additional solid layer is loaded:

*   `data/biome_impl/temple/solid.png`

## Background Element

A background sprite is consistently loaded for all variants:

*   `data/biome_impl/temple/wall_background.png` at `x-1, y - 30`.

```lua
function spawn_altar_top(x, y, is_solid)
	SetRandomSeed( x, y )
	local randomtop = Random( 1, 50 )
	local file_visual = "data/biome_impl/temple/altar_top_visual.png"
	
	LoadBackgroundSprite( "data/biome_impl/temple/wall_background.png", x-1, y - 30, 35 )

	if( y > 12000 ) then
		LoadPixelScene( "data/biome_impl/temple/altar_top_boss_arena.png", file_visual, x, y-40, "", true )
	else
		if (randomtop == 5) then
			LoadPixelScene( "data/biome_impl/temple/altar_top_water.png", file_visual, x, y-40, "", true )
		elseif (randomtop == 8) then
			LoadPixelScene( "data/biome_impl/temple/altar_top_blood.png", file_visual, x, y-40, "", true )
		elseif (randomtop == 11) then
			LoadPixelScene( "data/biome_impl/temple/altar_top_oil.png", file_visual, x, y-40, "", true )
		elseif (randomtop == 13) then
			LoadPixelScene( "data/biome_impl/temple/altar_top_radioactive.png", file_visual, x, y-40, "", true )
		elseif (randomtop == 15) then
			LoadPixelScene( "data/biome_impl/temple/altar_top_lava.png", file_visual, x, y-40, "", true )
		else
			LoadPixelScene( "data/biome_impl/temple/altar_top.png", file_visual, x, y-40, "", true )
		end
	end	

	if is_solid then LoadPixelScene( "data/biome_impl/temple/solid.png", "", x, y-40+300, "", true ) end
end
```