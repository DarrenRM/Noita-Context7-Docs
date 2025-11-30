---
title: Physics Trap Scripting
category: scripts
---

# Physics Trap Scripting

This documentation outlines the Lua scripting functions used for creating and managing physics-based traps in Noita, primarily focusing on entity spawning and triggering mechanisms.

## Core Functions

### `electricity_receiver_switched( on )`

This function is designed to be called when an entity with an `ElectricityReceiverComponent` is switched. It handles spawning entities or enabling components based on variables stored within the entity.

**Key Attributes/Elements:**

*   **`on` (boolean):** Determines if the action should be performed (true) or not (false).
*   **`VariableStorageComponent`:** This component is crucial for defining the trap's behavior. It should contain variables like:
    *   **`entity_file` (string):** The path to the `.xml` file of the entity to spawn.
    *   **`offset_x` (integer):** Horizontal offset from the trap's position for the spawned entity.
    *   **`offset_y` (integer):** Vertical offset from the trap's position for the spawned entity.
    *   **`enable_component` (string):** The tag of a component to enable on the triggering entity.
*   **`EntityLoad( entity_file, x, y )`:** Spawns a new entity at the specified coordinates.
*   **`EntitySetComponentsWithTagEnabled( entity_id, tag, enable )`:** Enables or disables components on an entity based on their tag.

### `trigger_trap( trap_id, trap_x, trap_y )`

This function is responsible for activating a specific trap entity. It reads configuration from the trap's `VariableStorageComponent` to spawn an entity and then destroys the trap itself.

**Key Attributes/Elements:**

*   **`trap_id` (entity ID):** The unique identifier of the trap entity to be triggered.
*   **`trap_x`, `trap_y` (number):** The coordinates of the trap.
*   **`VariableStorageComponent`:** Used to define:
    *   **`entity_file` (string):** The path to the `.xml` file of the entity to spawn when the trap is triggered.
*   **`EntityLoad( entity_file, x, y )`:** Spawns the specified entity at the trap's location.
*   **`EntityLoad( "data/entities/misc/music_energy_100_10s.xml", trap_x, trap_y )`:** A hardcoded entity that is always spawned upon trap activation, likely for sound or visual effects.
*   **`EntityKill( trap_id )`:** Removes the trap entity from the game.

### `trigger_wand_pickup_trap( x, y )`

This function searches for entities tagged as "wand\_trap" and triggers them if the player's position is within a certain proximity. This is likely used for traps that activate when a wand is picked up or approached.

**Key Attributes/Elements:**

*   **`x`, `y` (number):** The player's current coordinates.
*   **`EntityGetWithTag( "wand_trap" )`:** Retrieves a list of all entities with the tag "wand\_trap".
*   **Proximity Check:** The function checks if the player is within a vertical range of 128 units and a horizontal range of 180 units from a "wand\_trap" entity.
*   **`trigger_trap( entity_id, trap_x, trap_y )`:** Called for any "wand\_trap" that meets the proximity criteria.

---