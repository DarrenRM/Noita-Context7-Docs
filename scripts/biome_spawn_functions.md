---
title: Biome Spawn Functions
category: scripts
---

# Biome Spawn Functions

This document details various Lua functions used for spawning entities and scene elements within Noita biomes. These functions are typically called by the game's biome generation system to populate the world.

## Key Spawn Functions

Here's a breakdown of the most commonly used and important spawn functions:

### `runestone_activate( entity_id )`

This function handles the activation logic for runestones. It toggles a "active" variable stored within the entity's `VariableStorageComponent`. When activated, it enables components tagged with "activate".

### `spawn_apparition( x, y )`

Spawns an "Apparition" entity at the given coordinates. It also has logic to potentially spawn candles or load a specific pixel scene (`grave.png`) based on a random state.

### `spawn_persistent_teleport( x, y )`

This function is intended to spawn persistent teleport entities. The current implementation is commented out, suggesting it might be a placeholder or an older version.

### `spawn_candles( x, y )`

Spawns a set of candles at the specified coordinates.

### `spawn_wands( x, y )`

Spawns items from the `g_items` list, offset horizontally. This is likely used for spawning wands.

### `spawn_potions( x, y )`

Spawns potions at the given coordinates. It includes logic to spawn a "potion_mimic" with a small chance, or a regular potion from the `potion_spawnlist`.

### `spawn_ghostlamp( x, y )`

Spawns a ghost lamp entity.

### `parallel_check( x, y )`

This function checks for entities in parallel worlds (worlds with negative Y coordinates). It has a chance to spawn "parallel_alchemist" or "parallel_tentacles" entities.

### `spawn_mimic_sign( x, y )`

Spawns a "mimic_sign" pixel scene. It uses raycasting to determine placement and ensure it's not obstructed.

### `spawn_heart( x, y )`

Spawns a heart pickup. It has special logic for Valentine's Day (February 14th) to reduce the spawn chance. It can also spawn chests (random, super, or leggy) or mimic chests.

### `spawn_potion_altar( x, y )`

Spawns a "potion_altar" pixel scene with a certain probability.

### `spawn_debug_mark( x, y )`

Spawns a debug marker entity.

### `spawn_portal( x, y )`

Spawns a teleport entity. The type of teleport spawned depends on the current `BIOME_NAME`.

### `spawn_end_portal( x, y )`

Spawns an end portal, specifically a `teleport_boss_arena.xml`.

### `spawn_runes( x, y )`

This function is commented out and likely a placeholder for rune spawning.

### `spawn_fullhp( x, y )`

Spawns a "heart_fullhp" pickup.

### `spawn_wand_trap( x, y )`

Spawns an acid-themed wand trap.

### `spawn_wand_trap_electricity_source( x, y )`

Spawns an electricity-themed wand trap building.

### `spawn_wand_trap_electricity( x, y )`

Spawns an electricity-themed wand trap prop.

### `spawn_wand_trap_ignite( x, y )`

Spawns an ignite-themed wand trap prop.

### `spawn_bigtorch( x, y )`

Spawns a large torch prop.

### `spawn_moon( x, y )`

Spawns a moon altar building.

### `spawn_collapse( x, y )`

Spawns loose chunks, likely for environmental destruction effects.

### `spawn_shopitem( x, y )`

Calls `generate_shop_item` to spawn a shop item.

## Helper Functions and Variables

The script also utilizes several helper functions and global variables:

*   **`dofile( "data/scripts/item_spawnlists.lua" )`**: Imports functions and definitions from `item_spawnlists.lua`, which likely contains definitions for item spawn lists and potentially global item variables.
*   **`SetRandomSeed( x, y )`**: Initializes the random number generator with coordinates to ensure deterministic spawning for specific locations.
*   **`ProceduralRandom( x, y )`**: A function for generating pseudo-random numbers based on coordinates, often used for probabilistic spawning.
*   **`EntityGetComponent( entity_id, component_name )`**: Retrieves components of a specific type from an entity.
*   **`ComponentGetValue( component_id, value_name )`**: Gets the value of a specific property within a component.
*   **`ComponentSetValue2( component_id, value_name, value )`**: Sets the value of a specific property within a component.
*   **`EntitySetComponentsWithTagEnabled( entity_id, tag, enabled )`**: Enables or disables components of an entity that have a specific tag.
*   **`SpawnApparition( x, y, level )`**: A core function for spawning apparitions.
*   **`LoadPixelScene( image_path, visual_path, x, y, tag, is_dynamic, is_editor_only )`**: Loads a pixel scene from image files, used for creating custom visual elements and structures.
*   **`SpawnPersistentTeleport( x, y )`**: Spawns a persistent teleport.
*   **`spawn( entity_name, x, y, velocity_x, velocity_y )`**: A generic function to spawn an entity by its name.
*   **`spawn_from_list( list_name, x, y )`**: Spawns an item from a predefined spawn list.
*   **`EntityLoad( entity_xml_path, x, y )`**: Loads an entity from its XML definition file.
*   **`GetParallelWorldPosition( x, y )`**: Gets the corresponding position in a parallel world.
*   **`Raytrace( x1, y1, x2, y2 )`**: Performs a raycast to detect collisions.
*   **`GameGetDateAndTimeLocal()`**: Retrieves the current local date and time.
*   **`BIOME_NAME`**: A global variable that holds the name of the current biome.
*   **`generate_shop_item( x, y, is_special, price )`**: A function likely responsible for generating shop items with specific properties.