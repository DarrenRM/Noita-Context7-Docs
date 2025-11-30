---
title: Broken Wand Throw Script
category: scripts/
---

# Broken Wand Throw Script

This script defines the behavior for a "broken wand" item when it's thrown. It primarily focuses on storing the number of spells it contains and the time it was thrown.

## Key Functionality

### `throw_item(from_x, from_y, to_x, to_y)`

This function is called when the broken wand entity is thrown.

*   **Purpose:** To initialize and store essential data for the broken wand's behavior after being thrown.
*   **Parameters:**
    *   `from_x`, `from_y`: The starting coordinates of the throw (not directly used in this script's logic but part of the standard throw event).
    *   `to_x`, `to_y`: The target coordinates of the throw (not directly used in this script's logic but part of the standard throw event).
*   **Core Actions:**
    1.  **Get Entity ID:** Retrieves the unique identifier for the broken wand entity.
    2.  **Store Spell Amount:**
        *   Uses `get_variable_storage_component` to access a storage component named `"spells_remaining"`.
        *   Sets the integer value of this component to `spell_amount` (which is defined as `18` at the top of the script). This indicates how many spells the broken wand will cast.
    3.  **Store Throw Time:**
        *   Uses `get_variable_storage_component` to access a storage component named `"throw_time"`.
        *   Sets the integer value of this component to `GameGetFrameNum()`. This records the game frame number when the wand was thrown, likely for timing subsequent actions.

## Configuration

### `spell_amount`

*   **Type:** Integer
*   **Default Value:** `18`
*   **Description:** Determines the number of spells a broken wand will cast when it's activated after being thrown.

---

**Note:** This script relies on other scripts (like `broken_wand_spells.lua`) to utilize the stored `spells_remaining` and `throw_time` variables.