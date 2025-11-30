---
title: Aggressive Potion Item Definition
category: scripts
---

# Aggressive Potion Item Definition

This document details the configuration for the "Aggressive Potion" item in Noita, focusing on its material properties and how it's initialized.

## Item Properties

The `potions` table defines the various materials that can be assigned to an aggressive potion, along with their associated costs.

### Potion Material Options

| Material Name             | Cost | Description                                     |
| :------------------------ | :--- | :---------------------------------------------- |
| `lava`                    | 300  | A fiery, damaging liquid.                       |
| `water`                   | 200  | Basic liquid.                                   |
| `blood`                   | 200  | Biological fluid.                               |
| `alcohol`                 | 200  | Flammable liquid.                               |
| `oil`                     | 200  | Combustible liquid.                             |
| `slime`                   | 200  | Sticky, potentially damaging liquid.            |
| `acid`                    | 400  | Corrosive liquid that damages entities.         |
| `radioactive_liquid`      | 300  | Liquid that inflicts radiation damage.          |
| `gunpowder_unstable`      | 400  | Highly explosive material.                      |
| `liquid_fire`             | 400  | A persistent source of fire damage.             |
| `magic_liquid_teleportation` | 500  | Grants teleportation effects.                   |
| `magic_liquid_berserk`    | 500  | Induces a berserk state in affected entities.   |
| `magic_liquid_charm`      | 800  | Causes entities to become charmed/friendly.     |
| `blood_cold`              | 400  | Freezing variant of blood.                      |

*Note: The `cost` attribute likely influences the item's rarity or shop price.*

## Initialization Logic

The `init` function is responsible for setting up the aggressive potion when it is spawned in the game.

### Key Initialization Steps

1.  **Seed Randomization:** The function first retrieves the entity's position (`x`, `y`) and uses it, along with the current game frame number, to generate a random seed. This ensures that the potion's material is consistent across different game sessions if spawned at the same location and frame.
2.  **Material Selection:** A random material is selected from the `potions` table using the `random_from_array` utility function.
3.  **Material Assignment:** The chosen material is then added to the entity's inventory with a quantity of 1000 units using `AddMaterialInventoryMaterial`. This effectively defines the liquid content of the potion.

```lua
function init( entity_id )
	local x,y = EntityGetTransform( entity_id )
	SetRandomSeed( x + GameGetFrameNum(), y )
	-- so that all the potions will be the same in every position with the same seed
	local potion = random_from_array( potions )

	AddMaterialInventoryMaterial( entity_id, potion.material, 1000 )
end
```