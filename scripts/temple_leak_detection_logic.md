---
title: Temple Leak Detection Logic
category: scripts
---

# Temple Leak Detection Logic

This script defines the behavior when a "leak" is detected within the temple area in Noita. A leak typically signifies the player has disturbed a sacred area or angered the gods.

## Core Functionality

The primary function `material_area_checker_failed` is triggered when a leak is detected. It handles various game state changes and player feedback.

### Key Actions on Leak Detection:

*   **Check for Divine Favor:** If the player has achieved "TEMPLE_PEACE_WITH_GODS", a specific message and sound are triggered, indicating divine displeasure.
*   **Spawn Guardian:** If a temple guardian hasn't been spawned yet for this leak, it will be summoned. This is tracked by the `TEMPLE_SPAWN_GUARDIAN` global variable.
*   **Player Feedback:**
    *   Prints important messages to the player, varying based on the number of player deaths (`STEVARI_DEATHS`).
    *   Triggers an achievement (`GODS_ENRAGED`) if the gods are "very angry".
    *   Plays a sound effect indicating divine anger.
    *   Initiates a screen shake to emphasize the event.
*   **Mark Leak as Handled:** A unique global variable (`TEMPLE_LEAKED_` followed by a temple position ID) is set to "1" to prevent repeated triggering of the same leak event.

### Global Variables Used:

| Variable Name             | Description                                                                                             |
| :------------------------ | :------------------------------------------------------------------------------------------------------ |
| `TEMPLE_PEACE_WITH_GODS`  | Indicates if the player has achieved peace with the temple gods.                                        |
| `TEMPLE_SPAWN_GUARDIAN`   | Flag to track if a guardian has already been spawned for a leak.                                        |
| `STEVARI_DEATHS`          | Tracks the number of player deaths, influencing the severity of messages.                               |
| `TEMPLE_LEAKED_[ID]`      | Unique identifier for each temple leak, set to "1" once the leak event has been processed.              |
| `TEMPLE_PERK_COUNT`       | (Commented out) Intended to track and potentially reduce player perks upon angering the gods.           |

### Functions Called:

*   `dofile_once()`: For including utility and shared temple scripts.
*   `GlobalsGetValue()`: To retrieve the current state of global variables.
*   `GamePrintImportant()`: Displays critical messages to the player.
*   `GamePlaySound()`: Plays sound effects.
*   `temple_pos_to_id()`: Converts temple coordinates to a unique ID.
*   `temple_spawn_guardian()`: Spawns a temple guardian entity.
*   `GameScreenshake()`: Triggers screen shaking.
*   `GameGiveAchievement()`: Awards achievements to the player.
*   `EntityGetClosestWithTag()`: (Commented out) Used to find the closest entity with a specific tag.
*   `EntityKill()`: (Commented out) Used to destroy entities.

## Commented-Out Code

The script contains commented-out sections that represent previous or experimental logic. Notably, there's a significant block that was intended to remove player perks when the gods are angered. This functionality is currently disabled.