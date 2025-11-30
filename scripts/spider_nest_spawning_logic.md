---
title: Spider Nest Spawning Logic
category: scripts
---

---

# Spider Nest Spawning Logic

This script defines the behavior for a "Spider Nest" entity in Noita, specifically its logic for spawning enemies.

## Core Functionality

The primary purpose of this script is to periodically spawn "longleg" enemies near the nest, provided certain conditions are met.

## Key Attributes and Logic

### 1. Entity Initialization

- `entity_id`: Retrieves the unique identifier for the nest entity.
- `pos_x`, `pos_y`: Gets the current position of the nest.
- `SetRandomSeed`: Initializes the random number generator based on game frame and entity position for consistent randomness.

### 2. Spawn Chance

- `if( Random(0,100) < 75 )`: There is a 75% chance for the spawning logic to execute on any given frame.

### 3. Player Proximity Check

- `spawn_distance = 200`: Defines the radius within which the player must be for spawning to occur.
- `EntityGetClosestWithTag( pos_x, pos_y, "player_unit")`: Finds the closest player entity.
- `distance_sqrt < spawn_distance * spawn_distance`: Checks if the player is within the defined `spawn_distance`.

### 4. Spawn Limit

- `GetValueInteger("spawned", 0)`: Retrieves the current count of spawned enemies associated with this nest.
- `if (spawned_entities < 15)`: The nest will only spawn new enemies if the total count is less than 15.

### 5. Enemy Spawning

- `pos_x = pos_x + Random(-4,4)` and `pos_y = pos_y + Random(-4,4)`: Introduces a small random offset to the spawn position.
- `EntityLoad( "data/entities/animals/longleg.xml", pos_x, pos_y-12 )`: Loads and places a "longleg" enemy entity at the calculated position. The `y` coordinate is slightly adjusted to position the enemy below the nest.
- `edit_component( new_entity, "LuaComponent", function(comp,vars) vars.script_death = "" end)`: Modifies the spawned "longleg" entity. Specifically, it clears the `script_death` variable within its LuaComponent, potentially preventing default death script behaviors.
- `spawned_entities = spawned_entities + 1`: Increments the count of spawned enemies.
- `SetValueInteger("spawned", spawned_entities)`: Updates the stored count of spawned enemies for this nest.