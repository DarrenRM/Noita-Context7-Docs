---
title: Sun Egg Kill Counter
category: scripts
---

---

# Sun Egg Kill Counter

This script defines the `death` function, which is triggered when an entity with this script attached is destroyed. Its primary purpose is to increment a kill counter associated with a specific entity tagged as "seed_c".

## Key Functionality

The `death` function performs the following actions:

### 1. Entity Identification and Initialization
- Retrieves the `entity_id` of the entity being destroyed.
- Gets the `pos_x` and `pos_y` coordinates of the entity.
- Initializes a random seed based on game frame number and entity position/ID for potential future use (though not directly used in the current kill counting logic).

### 2. Target Entity Search
- Searches for entities with the tag "seed_c". This tag likely identifies the "Sun Egg" or a related entity responsible for tracking kills.

### 3. Kill Counter Increment
- If an entity with the "seed_c" tag is found:
    - It selects the first found entity (`eid`).
    - It attempts to find a `VariableStorageComponent` within this entity with the variable name "sunegg_kills".
    - If the component exists:
        - It retrieves the current integer value of "sunegg_kills".
        - It increments this value by 1.
        - It prints the new kill count to the console (for debugging purposes).
        - It updates the "sunegg_kills" variable in the `VariableStorageComponent` with the new incremented value.

## Key Attributes/Elements

| Attribute/Element | Description |
|---|---|
| `death( damage_type_bit_field, damage_message, entity_thats_responsible, drop_items )` | The main function triggered on entity destruction. |
| `GetUpdatedEntityID()` | Retrieves the ID of the entity executing the script. |
| `EntityGetTransform( entity_id )` | Gets the position (x, y) of an entity. |
| `SetRandomSeed( seed1, seed2 )` | Sets the random seed for subsequent random number generation. |
| `EntityGetWithTag( tag_name )` | Returns a list of entities that have the specified tag. |
| `"seed_c"` | The tag used to identify the target entity for kill counting. |
| `EntityGetFirstComponent( entity_id, component_name, variable_name )` | Retrieves the first component of a specific type and name from an entity. |
| `"VariableStorageComponent"` | The component type used to store custom variables. |
| `"sunegg_kills"` | The name of the variable within `VariableStorageComponent` that stores the kill count. |
| `ComponentGetValue2( component, value_name )` | Retrieves the value of a specific variable within a component. |
| `ComponentSetValue2( component, value_name, new_value )` | Sets the value of a specific variable within a component. |
| `print( message )` | Outputs a message to the game console. |