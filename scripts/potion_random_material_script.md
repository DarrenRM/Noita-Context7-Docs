---
title: Potion Random Material Script
category: scripts/
---

# Potion Random Material Script

This script defines the behavior for a potion entity that randomly generates its material upon being spawned.

## `init( entity_id )` Function

This function is called when the potion entity is initialized.

### Key Actions:

1.  **Seed Randomization:**
    *   `SetRandomSeed( x, y )`: Initializes the random number generator based on the entity's position. This ensures that if multiple potions spawn at the exact same coordinates, they will receive the same random material.

2.  **Material Selection:**
    *   A 50% chance determines whether the potion will be filled with a random liquid or a random sand.
    *   `CellFactory_GetAllLiquids( false )`: Retrieves a list of all available liquid materials.
    *   `CellFactory_GetAllSands( false )`: Retrieves a list of all available sand materials.
    *   `random_from_array( materials )`: Selects a single random material from the chosen list (liquids or sands).

3.  **Material Assignment:**
    *   `AddMaterialInventoryMaterial( entity_id, potion_material, 1000 )`: Assigns the randomly selected `potion_material` to the potion entity's inventory with a quantity of 1000.

### Attributes/Elements:

*   **`entity_id`**: The unique identifier for the potion entity.
*   **`x`, `y`**: The coordinates of the potion entity.
*   **`materials`**: A table that will hold either a list of liquids or sands.
*   **`potion_material`**: The randomly selected material to be added to the potion.
*   **`Random( 0, 100 )`**: Used to determine the 50% chance for liquid vs. sand.
*   **`CellFactory_GetAllLiquids( false )`**: Function to get all liquid materials.
*   **`CellFactory_GetAllSands( false )`**: Function to get all sand materials.
*   **`random_from_array( array )`**: Utility function to pick a random element from a table.
*   **`AddMaterialInventoryMaterial( entity_id, material_name, amount )`**: Function to add a specified amount of a material to an entity's inventory.