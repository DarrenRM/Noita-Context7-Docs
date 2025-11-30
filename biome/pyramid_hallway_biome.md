---
title: Pyramid Hallway Biome
category: biome
---

---

# Pyramid Hallway Biome

This document details the configuration for the Pyramid Hallway biome in Noita, focusing on its entity spawning and visual setup.

## Core Biome Initialization

The `init` function is responsible for loading the primary visual and material assets for the Pyramid Hallway.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/pyramid/hallway.png", "data/biome_impl/pyramid/hallway_visual.png", x, y, "", true )
	-- Fill in the background
	LoadBackgroundSprite("data/weather_gfx/background_pyramid.png", x, y)
	LoadBackgroundSprite("data/weather_gfx/background_pyramid.png", x, y + 256)
end
```

-   **`LoadPixelScene`**: Loads the main tilemap and visual layer for the hallway.
-   **`LoadBackgroundSprite`**: Adds the pyramid background to the scene.

## Entity Spawning Configurations

The following tables define the probability and types of entities that can spawn within the Pyramid Hallway. Each entry specifies:

-   `prob`: The probability of this specific entity or group of entities spawning.
-   `min_count`: The minimum number of entities to spawn.
-   `max_count`: The maximum number of entities to spawn.
-   `entity`: The XML file path for the entity to spawn.
-   `entities`: A list of entities to spawn, often used for groups or variations.
-   `offset_x`, `offset_y`: Adjustments to the spawn position.

### Small Enemies

```lua
g_small_enemies =
{
	total_prob = 0,
	{
		prob   		= 2.5, -- Placeholder, likely for air
		min_count	= 0,
		max_count	= 0,
		entity 	= ""
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/skullrat.xml"
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/skullfly.xml"
	},
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/acidshooter.xml"
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scorpion.xml"
	},
}
```

### Large Enemies

```lua
g_big_enemies =
{
	total_prob = 0,
	{
		prob   		= 2.5, -- Placeholder, likely for air
		min_count	= 0,
		max_count	= 0,
		entity 	= ""
	},
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/acidshooter.xml"
	},
	{
		prob   		= 0.07,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/phantom_a.xml"
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/skullfly.xml"
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/skullrat.xml"
	},
	{
		prob   		= 0.07,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/phantom_b.xml"
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scorpion.xml"
	},
}
```

### Statues

```lua
g_statues =
{
	total_prob = 0,
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/statue.xml"
	},
}
```

### Scorpions

```lua
g_scorpions =
{
	total_prob = 0,
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 1,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scorpion.xml"
	},
}
```

### Lamps

```lua
g_lamp =
{
	total_prob = 0,
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 0.6,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_torch_stand_blue.xml"
	},
}

g_lamp2 =
{
	total_prob = 0,
	{
		prob   		= 0.0, -- No spawn
		min_count	= 1,
		max_count	= 1,
		entity 	= ""
	},
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics/chain_torch_blue.xml"
	},
}
```

### Save Points

```lua
g_save =
{
	total_prob = 0,
	{
		prob   		= 0.5,
		min_count	= 0,
		max_count	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 0.8,
		min_count	= 1,
		max_count	= 1,
		offset_y	= -4,
		entity 	= "data/entities/buildings/save_point.xml"
	},
}
```

### Props

```lua
g_props =
{
	total_prob = 0,
	{
		prob   		= 0.2,
		min_count	= 0,
		max_count	= 0,
		offset_y 	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 0.5,
		min_count	= 1,
		max_count	= 1,
		offset_y	= -4,
		entity 	= "data/entities/props/physics_vase.xml"
	},
	{
		prob   		= 0.3,
		min_count	= 1,
		max_count	= 1,
		offset_y	= -4,
		entity 	= "data/entities/props/physics_vase_longleg.xml"
	},
}
```

### Unique Enemies

```lua
g_unique_enemy =
{
	total_prob = 0,
	{
		prob   		= 0.1,
		min_count	= 0,
		max_count	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		offset_x	= 2,
		entity 	= "data/entities/buildings/arrowtrap_right.xml"
	},
}

g_large_enemies = -- Note: This table is named 'g_large_enemies' but seems to spawn 'arrowtrap_left'
{
	total_prob = 0,
	{
		prob   		= 0.1,
		min_count	= 0,
		max_count	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		offset_x	= 1,
		entity 	= "data/entities/buildings/arrowtrap_left.xml"
	},
}
```

### Ghost Crystals

```lua
g_ghost_crystal =
{
	total_prob = 0,
	{
		prob   		= 0.9,
		min_count	= 0,
		max_count	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entities = {
			{
				min_count	= 1,
				max_count 	= 3,
				entity = "data/entities/animals/ghost.xml",
			},
			"data/entities/buildings/ghost_crystal.xml",
		}
	},
}
```

### Pressure Plates

```lua
g_pressureplates =
{
	total_prob = 0,
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/pressure_plate.xml"
	},
}
```

### Doors

```lua
g_doors =
{
	total_prob = 0,
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_templedoor.xml"
	},
}
```

### Candles

```lua
g_candles =
{
	total_prob = 0,
	{
		prob   		= 0.33,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_candle_1.xml"
	},
	{
		prob   		= 0.33,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_candle_2.xml"
	},
	{
		prob   		= 0.33,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics_candle_3.xml"
	},
}
```

### Scavengers

```lua
g_scavengers =
{
	total_prob = 0,
	{
		prob   		= 0.9,
		min_count	= 0,
		max_count	= 0,
		entity 	= "" -- Likely for no spawn
	},
	{
		prob   		= 0.2,
		min_count	= 1,
		max_count	= 3,
		entities 	= {
			"data/entities/animals/scavenger_smg.xml",
			"data/entities/animals/scavenger_grenade.xml",
			}
	},
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scavenger_leader.xml"
	},
	{
		prob   		= 0.1,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scavenger_clusterbomb.xml"
	},
	{
		prob   		= 0.05,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/animals/scavenger_poison.xml"
	},
}
```

### Ghost Lamps

```lua
g_ghostlamp =
{
	total_prob = 0,
	{
		prob   		= 1.0,
		min_count	= 1,
		max_count	= 1,
		entity 	= "data/entities/props/physics/chain_torch_ghostly.xml"
	},
}
```

## Pixel Scene Loading

These configurations define alternative pixel scenes that can be loaded within the biome.

### `g_pixel_scene_01`

```lua
g_pixel_scene_01 =
{
	total_prob = 0,
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/cathedral.png",
		visual_file		= "",
		background_file	= "",
		is_unique		= 0
	},
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/mining.png",
		visual_file		= "",
		background_file	= "",
		is_unique		= 0
	},
}
```

### `g_pixel_scene_02`

```lua
g_pixel_scene_02 =
{
	total_prob = 0,
	{
		prob   			= 0.5,
		material_file 	= "data/biome_impl/crypt/stairs_right.png",
		visual_file		= "",
		background_file	= "",
		is_unique		= 0
	},
}
```

### `g_pixel_scene_03`

```lua
g_pixel_scene_03 =
{
	total_prob = 0,
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/lavaroom.png",
		visual_file		= "data/biome_impl/crypt/lavaroom_visual.png",
		background_file	= "",
		is_unique		= 0
	},
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/pit.png",
		visual_file		= "data/biome_impl/crypt/pit_visual.png",
		background_file	= "",
		is_unique		= 0
	},
	{
		prob   			= 1.0,
		material_file 	= "data/biome_impl/crypt/symbolroom.png",
		visual_file		= "",
		background_file	= "",
		is_unique		= 0
	},
}
```

### `g_pixel_scene_04`

```lua
g_pixel_scene_04 =
{
	total_prob = 0,
	{
		prob   			= 0.5,
		material_file 	= "data/biome_impl/crypt/stairs_left.png",
		visual_file		= "",
		background_file	= "",
		is_unique		= 0
	},
}
```

## Spawn Functions

These functions are called by the game's director to spawn specific elements or trigger biome features.

-   **`spawn_small_enemies(x, y)`**: Spawns small enemies based on `g_small_enemies`.
-   **`spawn_big_enemies(x, y)`**: Spawns large enemies based on `g_big_enemies`.
-   **`spawn_statues(x, y)`**: Spawns statues based on `g_statues`.
-   **`spawn_lamp(x, y)`**: Spawns lamps based on `g_lamp`.
-   **`spawn_lamp2(x, y)`**: Spawns lamps based on `g_lamp2`.
-   **`spawn_props(x, y)`**: Spawns props based on `g_props`.
-   **`spawn_unique_enemy(x, y)`**: Spawns unique enemies based on `g_unique_enemy`.
-   **`spawn_large_enemies(x, y)`**: Spawns large enemies based on `g_large_enemies`.
-   **`spawn_ghost_crystal(x, y)`**: Spawns ghost crystals based on `g_ghost_crystal`.
-   **`spawn_pressureplates(x, y)`**: Spawns pressure plates based on `g_pressureplates`.
-   **`spawn_doors(x, y)`**: Spawns doors based on `g_doors`.
-   **`load_pixel_scene(x, y)`**: Loads pixel scenes based on `g_pixel_scene_01`.
-   **`load_pixel_scene2(x, y)`**: Loads pixel scenes based on `g_pixel_scene_02`.
-   **`load_pixel_scene3(x, y)`**: Loads pixel scenes based on `g_pixel_scene_03`.
-   **`load_pixel_scene4(x, y)`**: Loads pixel scenes based on `g_pixel_scene_04`.
-   **`spawn_scavengers(x, y)`**: Spawns scavengers based on `g_scavengers`.
-   **`spawn_scorpions(x, y)`**: Spawns scorpions based on `g_scorpions`.

The following spawn functions are defined but do not contain any implementation in this file:

-   `spawn_items(x, y)`
-   `spawn_chest(x, y)`
-   `spawn_save(x, y)`
-   `spawn_crawlers(x, y)`