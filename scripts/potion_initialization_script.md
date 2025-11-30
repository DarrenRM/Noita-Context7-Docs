---
title: Potion Initialization Script
category: scripts
---

# Potion Initialization Script

This script, `init_potion.lua`, handles the initialization of potion entities in Noita. It defines how a potion's material and capacity are set, ensuring consistency and allowing for dynamic adjustments.

## Core Functionality

The `init_potion` function takes an `entity_id` and an optional `potion_material` as input. It performs the following key actions:

### 1. Seed Randomness
```lua
SetRandomSeed( x, y )
```
This line ensures that potions placed at the same coordinates will always have the same properties. This is crucial for deterministic world generation and consistent gameplay.

### 2. Load Potion Material
The script attempts to retrieve the `potion_material` from a `VariableStorageComponent` attached to the entity. This allows potion materials to be defined externally, such as in entity XML files.

```lua
local components = EntityGetComponent( entity_id, "VariableStorageComponent" )

if( components ~= nil ) then
	for key,comp_id in pairs(components) do
		local var_name = ComponentGetValue( comp_id, "name" )
		if( var_name == "potion_material") then
			potion_material = ComponentGetValue( comp_id, "value_string" )
		end
	end
end
```

### 3. Determine Total Capacity
The script fetches a global value for `EXTRA_POTION_CAPACITY_LEVEL`. If this value exceeds the default of 1000, it indicates an increased capacity for the potion.

```lua
local total_capacity = tonumber( GlobalsGetValue( "EXTRA_POTION_CAPACITY_LEVEL", "1000" ) ) or 1000
```

### 4. Adjust Material Sucker Component
If `total_capacity` is greater than 1000, the script finds and updates the `MaterialSuckerComponent` to reflect this increased capacity.

```lua
if ( total_capacity > 1000 ) then
	local comp = EntityGetFirstComponentIncludingDisabled( entity_id, "MaterialSuckerComponent" )

	if ( comp ~= nil ) then
		ComponentSetValue( comp, "barrel_size", total_capacity )
	end

	EntityAddTag( entity_id, "extra_potion_capacity" )
end
```
A tag `extra_potion_capacity` is also added to the entity for potential further logic.

### 5. Add Material to Inventory
Finally, the script adds the determined `potion_material` to the entity's inventory with the calculated `total_capacity`.

```lua
AddMaterialInventoryMaterial( entity_id, potion_material, total_capacity )
```

## Key Components Involved

*   **`VariableStorageComponent`**: Used to store and retrieve custom variables, specifically the `potion_material` in this case.
*   **`MaterialSuckerComponent`**: A component that manages the capacity of a material sucker, which is adjusted for potions with extra capacity.
*   **`GlobalsGetValue`**: A function to access global game variables, used here for `EXTRA_POTION_CAPACITY_LEVEL`.
*   **`AddMaterialInventoryMaterial`**: A function to add a specific material to an entity's inventory with a given quantity.