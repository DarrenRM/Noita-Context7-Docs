---
title: Temple Altar Right Biome
category: biome
---

# Temple Altar Right Biome

This document describes the `temple_altar_right.xml` file, which defines a biome in Noita.

## Topology

The `Topology` element defines the core characteristics of the biome.

### Key Attributes:

*   **name**: `$biome_holymountain` - Internal identifier for the biome.
*   **type**: `BIOME_WANG_TILE` - Indicates this biome uses Wang Tiles for its generation.
*   **background_image**: `data/weather_gfx/background_cave_02.png` - Specifies the background image for this biome.
*   **lua_script**: `data/scripts/biomes/temple_altar_right.lua` - Links to the Lua script that controls the biome's behavior and generation logic.
*   **wang_map_width**: `256` - The width of the Wang map used for generation.
*   **wang_map_height**: `256` - The height of the Wang map used for generation.
*   **audio_ambience**: `temple` - The ambient soundscape associated with this biome.

## Materials

The `Materials` element defines the materials present within this biome.

### Key Attributes:

*   **name**: `temple` - The name of the material set used in this biome.

```xml
<Biome>
  <Topology 
    name="$biome_holymountain"
	  type="BIOME_WANG_TILE"
    background_image="data/weather_gfx/background_cave_02.png"
    background_use_neighbor="0"
    wang_template_file="" 
    lua_script="data/scripts/biomes/temple_altar_right.lua"
    wang_map_width="256"
    wang_map_height="256"
	  limit_background_image="0"
    coarse_map_force_terrain="1"
    pixel_scene="1"
    noise_biome_edges="0"
    audio_ambience="temple">
  </Topology>

  <!------------ MATERIALS -------------------->
  <Materials 
    name="temple" 
     >
   </Materials>
</Biome>
```