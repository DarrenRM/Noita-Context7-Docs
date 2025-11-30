---
title: Biome Map Generation
category: scripts/
---

# Biome Map Generation

This script defines the generation logic for the Noita biome map, determining the placement and types of biomes within the game world. It uses a pixel-based approach to define biome regions and can incorporate specific room placements.

## Key Biome Definitions

These constants represent different biome types using ARGB color codes.

*   `snowcave`: `0xff1775d5`
*   `excavation_site`: `0xff124445`
*   `coalmine`: `0xffd57917`
*   `hills`: `0xff36d517`
*   `shop_room`: `0xff3d5ab2`
*   `temple_altar_secret`: `0xff93cb5c`

## Map Dimensions and Loading

The script sets the overall dimensions of the biome map and loads a base image for its structure.

*   `w`: Width of the biome map (e.g., `64`).
*   `h`: Height of the biome map (e.g., `48`).
*   `BiomeMapSetSize( w, h )`: Sets the dimensions of the biome map.
*   `BiomeMapLoadImage( 0, 0, "data/biome_impl/biome_map_metagame.png" )`: Loads a base image to define the initial biome layout.

## Special Room Placement

The script defines a set of potential locations for special rooms and randomly selects one to place them.

### Location Data

A table containing arrays of coordinates, where each inner array represents a pair of locations for specific rooms.

```lua
local locations =
{
	{ -- Location Set 1
		{23,21}, -- Coordinate for Room 1
		{32,19}, -- Coordinate for Room 2
	},
	{ -- Location Set 2
		{38,25},
		{32,23},
	},
	-- ... more location sets
}
```

### Random Room Selection

*   `SetRandomSeed( 0, 0 )`: Initializes the random number generator.
*   `local secretlevel = Random( 1,5 )`: Selects a random biome set from the `locations` table.
*   `local loc = locations[secretlevel]`: Retrieves the chosen location set.
*   `local loc1 = loc[1]` and `local loc2 = loc[2]`: Extracts the coordinates for the two rooms.
*   `BiomeMapSetPixel( loc1[1], loc1[2], shop_room )`: Places the `shop_room` at the first coordinate.
*   `BiomeMapSetPixel( loc2[1], loc2[2], temple_altar_secret )`: Places the `temple_altar_secret` at the second coordinate.

## Biome Layering (Commented Out Example)

The commented-out section demonstrates a procedural approach to assigning biomes based on vertical position (`y` coordinate). This can be used as an alternative or supplementary method to image-based biome generation.

```lua
--[[
for y=0,h-1 do
	for x=0,w-1 do

		if y > 19 then
			BiomeMapSetPixel( x, y, snowcave )
		elseif y > 16 then
			BiomeMapSetPixel( x, y, excavation_site )
		elseif y > 14 then
			BiomeMapSetPixel( x, y, coalmine )
		else
			BiomeMapSetPixel( x, y, hills )
		end

	end
end
]]--
```