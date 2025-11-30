---
title: New Game Plus Logic
category: scripts
---

# New Game Plus Logic

This script handles the logic for initiating a "New Game Plus" mode in Noita. It increments the New Game Plus counter, scales enemy difficulty, and modifies player damage intake for subsequent playthroughs.

## Core Functionality

The `do_newgame_plus()` function orchestrates the New Game Plus experience.

### Key Actions:

1.  **Increment New Game Plus Counter:**
    *   Retrieves the current "NEW\_GAME\_PLUS\_COUNT" from session numbers.
    *   Increments this count by 1.
    *   Saves the updated count back to session numbers.

2.  **Scale Enemy Difficulty:**
    *   Sets the "DESIGN\_SCALE\_ENEMIES" session number to "1", indicating that enemy scaling is active.
    *   Calculates and sets session numbers for enemy health scaling:
        *   `DESIGN_NEW_GAME_PLUS_HP_SCALE_MIN`: Minimum HP multiplier for enemies.
        *   `DESIGN_NEW_GAME_PLUS_HP_SCALE_MAX`: Maximum HP multiplier for enemies.
        *   `DESIGN_NEW_GAME_PLUS_ATTACK_SPEED`: Attack speed multiplier for enemies.

3.  **Modify Player Damage Intake:**
    *   Locates the player entity.
    *   Iterates through the player's `DamageModelComponent`.
    *   Significantly increases the player's vulnerability to various damage types.

4.  **Load New Game Plus Biome Map:**
    *   Loads a specific biome map designed for New Game Plus playthroughs using `BiomeMapLoad_KeepPlayer`.

5.  **Clean Up Biome Entrances:**
    *   Uses `LoadPixelScene` to clear specific biome entrances, ensuring a clean transition.

6.  **Display New Game Plus Indicator:**
    *   Constructs a message indicating the current New Game Plus level (e.g., "New Game Plus +++").
    *   Displays this message prominently using `GamePrintImportant`.

## Player Damage Modification

The script significantly increases the player's damage taken from most sources.

### Damage Multiplier Adjustments:

| Damage Type   | Original Multiplier | New Multiplier | Notes                               |
| :------------ | :------------------ | :------------- | :---------------------------------- |
| `melee`       | Varies              | `* 3`          | Melee damage taken is tripled.      |
| `projectile`  | Varies              | `* 2`          | Projectile damage taken is doubled. |
| `explosion`   | Varies              | `* 2`          | Explosion damage taken is doubled.  |
| `electricity` | Varies              | `* 2`          | Electricity damage taken is doubled.|
| `fire`        | Varies              | `* 2`          | Fire damage taken is doubled.       |
| `drill`       | Varies              | `* 2`          | Drill damage taken is doubled.      |
| `slice`       | Varies              | `* 2`          | Slice damage taken is doubled.      |
| `ice`         | Varies              | `* 2`          | Ice damage taken is doubled.        |
| `radioactive` | Varies              | `* 2`          | Radioactive damage taken is doubled.|
| `poison`      | Varies              | `* 3`          | Poison damage taken is tripled.     |
| `healing`     | Varies              | Unchanged      | Healing is not affected.            |
| `physics_hit` | Varies              | Unchanged      | Physics hit damage is not affected. |

**Note:** The exact original multiplier values vary per player save. The script applies the multiplicative increase to whatever the current value is.

## Session Numbers Used

This script relies on and modifies several session numbers to track and control game state.

| Session Number                  | Description                                                              | Read/Write |
| :------------------------------ | :----------------------------------------------------------------------- | :--------- |
| `NEW_GAME_PLUS_COUNT`           | Tracks the number of times New Game Plus has been initiated.             | Read/Write |
| `DESIGN_SCALE_ENEMIES`          | Flag to enable enemy difficulty scaling.                                 | Write      |
| `DESIGN_NEW_GAME_PLUS_HP_SCALE_MIN` | Minimum HP multiplier for enemies in New Game Plus.                      | Write      |
| `DESIGN_NEW_GAME_PLUS_HP_SCALE_MAX` | Maximum HP multiplier for enemies in New Game Plus.                      | Write      |
| `DESIGN_NEW_GAME_PLUS_ATTACK_SPEED` | Attack speed multiplier for enemies in New Game Plus.                    | Write      |

## Biome Loading

The script specifies custom biome loading for New Game Plus.

*   **Biome Map:** `data/biome_impl/biome_map_newgame_plus.lua`
*   **Pixel Scenes:** `data/biome/_pixel_scenes_newgame_plus.xml`