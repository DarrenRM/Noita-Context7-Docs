---
title: Coalmine Debug Spawns
category: scripts
---

# Coalmine Debug Spawns

This script provides debugging tools for spawning items within the Coalmine biome. It leverages existing biome definitions and debug functions to facilitate item placement for testing purposes.

## Key Functions and Elements

### `dofile("data/scripts/biomes/coalmine.lua")`
This line ensures that the necessary definitions and functions related to the Coalmine biome are loaded and available for use.

### `DEBUG_GetMouseWorld()`
Retrieves the current mouse cursor's world coordinates. This is crucial for determining where to spawn entities.

### `EntityLoad( "data/entities/items/chest.xml", mouse_x, mouse_y - 20 )`
Loads and spawns a `chest.xml` entity at a specific location relative to the mouse cursor. This is used to initialize spawnable items.

### `g_items`
A global variable (presumably defined in `coalmine.lua`) that holds a collection of items to be spawned.

### `spawn(g_items, mouse_x, mouse_y)`
A loop that spawns a specified number of items from the `g_items` collection at the mouse cursor's location.

### `SpawnActionItem( mouse_x, mouse_y, 0 )`
A function that spawns "action items" at the given coordinates. The third argument (0) likely represents a rotation or other parameter.

## Usage Example

The script demonstrates spawning:
*   A chest entity.
*   Multiple items from the `g_items` collection.
*   Numerous "action items."

This allows developers to quickly populate a test environment within the Coalmine biome with various items for debugging and testing mod interactions.