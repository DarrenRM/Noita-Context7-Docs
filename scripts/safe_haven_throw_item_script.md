---
title: Safe Haven Throw Item Script
category: scripts
---

---

# Safe Haven Throw Item Script

This script defines the behavior for an item that, when thrown, spawns a "safe haven" at its destination. It handles storing information about the throw for the corresponding spawn script.

## Key Functions

### `throw_item(from_x, from_y, to_x, to_y)`

This function is called when the item is thrown.

*   **`from_x`, `from_y`**: The coordinates from which the item was thrown.
*   **`to_x`, `to_y`**: The coordinates to which the item is thrown.

#### Core Logic:

1.  **Enable Throw Components**: Activates components tagged with `"enabled_on_throw"`.
2.  **Store Throw Time**: Records the current game frame number in a variable storage component named `"throw_time"`. This is used by `safe_haven_spawn.lua`.
3.  **Store Player Health**:
    *   Initializes `hp` to `4.0`.
    *   Finds the closest player entity.
    *   If a player is found, it reads the player's maximum health (`max_hp`) and stores it in a variable storage component named `"player_hp"`.

## Key Components & Variables

*   **`enabled_on_throw`**: A tag used to enable specific components when the item is thrown.
*   **`throw_time`**: A variable storage component storing the game frame number of the throw.
*   **`player_hp`**: A variable storage component storing the player's maximum health at the time of the throw.
*   **`player_unit`**: A tag used to identify player entities.
*   **`DamageModelComponent`**: A component that holds damage-related information, including maximum health.