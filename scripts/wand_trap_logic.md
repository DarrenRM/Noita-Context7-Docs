---
title: Wand Trap Logic
category: scripts
---

---

# Wand Trap Logic

This script defines the behavior for wand traps in Noita, specifically how they are triggered and what actions they perform.

## Core Functions

### `trigger_trap(trap_id, trap_x, trap_y)`

This function is called when a wand trap is activated. It handles the entity loading and destruction associated with the trap.

*   **`trap_id`**: The unique identifier of the wand trap entity.
*   **`trap_x`, `trap_y`**: The world coordinates where the trap is located.

**Key Actions:**

1.  **Find `VariableStorageComponent`**: It searches for components attached to the trap that store variables.
2.  **Load Entity from `entity_file`**: If a variable named `"entity_file"` is found, its string value (which is an entity file path) is used to load a new entity at the trap's location. This is the primary mechanism for spawning the "wand" or other effects.
3.  **Load Music Entity**: A specific music entity (`"data/entities/misc/music_energy_100_10s.xml"`) is always loaded at the trap's location upon activation.
4.  **Destroy Trap**: The wand trap entity itself is then destroyed.

### `trigger_wand_pickup_trap(x, y)`

This function is responsible for detecting if a player's action (like picking up a wand) should trigger any nearby wand traps.

*   **`x`, `y`**: The player's current world coordinates.

**Key Actions:**

1.  **Find Wand Traps**: It retrieves all entities tagged with `"wand_trap"`.
2.  **Iterate and Check Proximity**: For each found wand trap, it compares the player's coordinates (`x`, `y`) with the trap's coordinates (`trap_x`, `trap_y`).
3.  **Trigger Condition**: A trap is triggered if:
    *   The vertical distance (`y - trap_y`) is less than 128 units.
    *   The horizontal distance (`math.abs(x - trap_x)`) is less than 180 units.
4.  **Call `trigger_trap`**: If the proximity conditions are met, the `trigger_trap` function is called for that specific trap.

## Key Attributes/Elements

*   **`VariableStorageComponent`**: Crucial for defining what entity gets spawned by the trap. The variable name `"entity_file"` is specifically looked for.
*   **`"entity_file"` variable**: Stores the path to the `.xml` file of the entity to be spawned (e.g., a wand).
*   **`"data/entities/misc/music_energy_100_10s.xml"`**: A hardcoded entity that is always spawned when a trap is triggered, likely for audio or visual feedback.
*   **`"wand_trap"` tag**: Used to identify all wand trap entities in the game world.
*   **Proximity Detection**: The `trigger_wand_pickup_trap` function uses specific distance thresholds (128 vertical, 180 horizontal) to determine if a trap should be activated.