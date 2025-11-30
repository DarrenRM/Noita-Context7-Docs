---
title: Orb Room 09 - Winter Cave
category: biome
---

# Orb Room 09 - Winter Cave

This document details the configuration for Orb Room 09, a specific biome variant found within Noita's winter cave environments. It focuses on the entities and visual elements loaded when this room is generated.

## Core Configuration

*   **`CHEST_LEVEL`**: `3` - Indicates the general tier or difficulty level associated with chests found in this room.
*   **`dofile_once`**: Several utility and shared biome scripts are loaded to ensure consistent functionality and access to common functions.

## Spawn Functions

The following spawn functions are defined but are empty in this specific configuration, meaning they do not spawn any entities by default. This suggests that the primary spawning logic for this orb room is handled elsewhere or through specific `EntityLoad` calls.

*   `spawn_small_enemies`
*   `spawn_big_enemies`
*   `spawn_items`
*   `spawn_props`
*   `spawn_props2`
*   `spawn_props3`
*   `spawn_lamp`
*   `load_pixel_scene`
*   `load_pixel_scene2`
*   `spawn_unique_enemy`
*   `spawn_unique_enemy2`
*   `spawn_unique_enemy3`
*   `spawn_ghostlamp`
*   `spawn_candles`
*   `spawn_potions`
*   `spawn_wands`

## Initialization (`init`)

The `init` function is responsible for setting up the visual and structural elements of the orb room.

```lua
function init( x, y, w, h )
	LoadPixelScene( "data/biome_impl/orbroom.png", "data/biome_impl/orbroom_visual.png", x, y, "data/biome_impl/orbroom_background.png", true )
end
```

*   **`LoadPixelScene`**: This is the primary function call that loads the visual representation of the orb room.
    *   `data/biome_impl/orbroom.png`: The base pixel data for the room's layout.
    *   `data/biome_impl/orbroom_visual.png`: Defines the visual appearance and textures.
    *   `x`, `y`: The coordinates where the scene is loaded.
    *   `data/biome_impl/orbroom_background.png`: The background image for the room.
    *   `true`: A boolean flag, likely indicating whether to use parallax scrolling or other advanced background features.

## Orb Spawning (`spawn_orb`)

This function handles the placement of the main orb and associated items within the room.

```lua
function spawn_orb(x, y)
	EntityLoad( "data/entities/items/orbs/orb_09.xml", x, y )
	--EntityLoad( "data/entities/items/pickup/heart_better.xml", x + 20, y ) -- Commented out
	EntityLoad( "data/entities/items/books/book_09.xml", x - 30, y + 40 )
	EntityLoad( "data/entities/misc/music_energy_000.xml", x, y - 10 )

	spawn_material_checker( x - 197, y - 11, "magic_liquid_random_polymorph", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/09_02.xml", x, y - 100 )
	spawn_material_checker( x + 198, y - 11, "magic_liquid_random_polymorph", "data/scripts/biomes/orbrooms/orbroom_shared.lua", "data/particles/image_emitters/orbrooms/09_02.xml", x, y - 100 )

	EntityLoad( "data/entities/particles/gold_dust.xml", x, y )
end
```

*   **`EntityLoad`**:
    *   `data/entities/items/orbs/orb_09.xml`: The primary orb entity for this room.
    *   `data/entities/items/books/book_09.xml`: A specific book entity, likely related to the orb's theme.
    *   `data/entities/misc/music_energy_000.xml`: A music or ambient effect entity.
    *   `data/entities/particles/gold_dust.xml`: A particle effect, likely for visual flair.
*   **`spawn_material_checker`**: This function is called twice to create two "material checker" entities. These are likely used to detect or interact with specific liquids or materials within the room.
    *   **Liquid Type**: `magic_liquid_random_polymorph` - Indicates that these checkers are associated with polymorphing liquids.
    *   **Shared Script**: `data/scripts/biomes/orbrooms/orbroom_shared.lua` - Suggests these checkers utilize logic defined in a shared orb room script.
    *   **Particle Emitter**: `data/particles/image_emitters/orbrooms/09_02.xml` - Links specific particle effects to these checkers.
    *   **Placement**: The coordinates are offset from the main orb's position (`x`, `y`), suggesting they are placed on either side of the orb.