---
title: Handgun Procedural Generation Script
category: scripts
---

# Handgun Procedural Generation Script

This script defines the procedural generation logic for the Handgun in Noita. It's a simple implementation that primarily focuses on setting the entity's transform and potentially its sprite, though the sprite randomization is commented out.

## Key Functionality

### `generate_gun()`

This function is responsible for the procedural generation of the handgun.

*   **Entity ID Retrieval:** `GetUpdatedEntityID()` retrieves the unique identifier for the handgun entity.
*   **Position Retrieval:** `EntityGetTransform( entity_id )` gets the current `x` and `y` coordinates of the entity.
*   **Random Seed:** `SetRandomSeed( x, y )` initializes the random number generator based on the entity's position, ensuring consistent results for the same location.
*   **Ability Component:** `EntityGetFirstComponent( entity_id, "AbilityComponent" )` retrieves the `AbilityComponent` associated with the handgun. This component is crucial for defining the gun's abilities.
*   **Sprite Setting (Commented Out):** The line `-- SetItemSprite( entity_id, ability_comp, "data/items_gfx/gungen_guns/handgun_", Random( 0, 7 ) )` is commented out. If enabled, it would procedurally select a sprite for the handgun from a predefined set of graphics.

## Usage

The `generate_gun()` function is called directly at the end of the script, meaning it executes when the handgun is spawned in the game.

```lua
-- This is not a very good way of generating these, way too much randomness...
dofile('data/scripts/gun/procedural/gun_utilities.lua')


function generate_gun()
	local entity_id = GetUpdatedEntityID()
	local x, y = EntityGetTransform( entity_id )
	SetRandomSeed( x, y )
	local ability_comp = EntityGetFirstComponent( entity_id, "AbilityComponent" )
	-- It's better if don't randomize the start pistol
	-- SetItemSprite( entity_id, ability_comp, "data/items_gfx/gungen_guns/handgun_", Random( 0, 7 )  )
end

generate_gun()
```