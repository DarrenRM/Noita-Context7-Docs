---
title: Secret Potion Definitions
category: scripts
---

# Secret Potion Definitions

This script defines a collection of "secret" potions that can be generated in the game. These potions are associated with specific materials and have a set cost.

## Potion Definitions

The `potions` table contains an array of potion objects, each defined by its `material` and `cost`.

```lua
potions =
{
	{
		material="magic_liquid_hp_regeneration_unstable",
		cost=300,
	},
	{
		material="blood_worm",
		cost=300,
	},
	{
		material="gold",
		cost=300,
	},
	--[[
	{
		material="creepy_liquid",
		cost=300,
	},
	]]--
	{
		material="snow",
		cost=300,
	},
	{
		material="glowshroom",
		cost=300,
	},
	{
		material="bush_seed",
		cost=300,
	},
	{
		material="cement",
		cost=300,
	},
	{
		material="salt",
		cost=300,
	},
	{
		material="sodium",
		cost=300,
	},
	{
		material="mushroom_seed",
		cost=300,
	},
	{
		material="plant_seed",
		cost=300,
	},
	{
		material="urine",
		cost=300,
	},
	{
		material="purifying_powder",
		cost=300,
	},
}
```

### Key Attributes

*   **material**: The internal name of the material that constitutes the potion. This determines the potion's properties and effects.
*   **cost**: The in-game cost associated with this potion.

**Note:** The `creepy_liquid` entry is commented out, indicating it's currently disabled or not intended for use.

## Initialization Function

The `init` function is responsible for setting up the potion when it's spawned in the game.

### `init( entity_id )`

*   **entity\_id**: The unique identifier for the potion entity.

This function performs the following actions:
1.  Retrieves the entity's position (`x`, `y`).
2.  Sets a random seed based on the entity's position to ensure consistent potion generation at the same location.
3.  Selects a random potion from the `potions` array using `random_from_array`.
4.  Adds the selected potion's material to the entity's inventory with a quantity of 1000.

```lua
function init( entity_id )
	local x,y = EntityGetTransform( entity_id )
	SetRandomSeed( x, y )
	-- so that all the potions will be the same in every position with the same seed
	local potion = random_from_array( potions )

	AddMaterialInventoryMaterial( entity_id, potion.material, 1000 )
end
```