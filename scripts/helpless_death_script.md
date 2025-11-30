---
title: Helpless Death Script
category: scripts
---

---

# Helpless Death Script

This script defines the behavior for when a "helpless" entity dies in Noita. It primarily focuses on tracking "helpless kills" and triggering a special explosion if the "Boss Spirit" is dead.

## Core Functionality

The `death` function is the main entry point for this script. It's called when an entity with this script attached dies.

### Key Attributes & Logic

*   **`anger` Tracking:**
    *   A global variable `HELPLESS_KILLS` is incremented each time this `death` function is called.
    *   This variable is initialized to "1" if it doesn't exist.
    *   This suggests a mechanic where repeated "helpless" deaths might influence game behavior or trigger events.

*   **Boss Spirit Condition:**
    *   Checks the global variable `BOSS_SPIRIT_DEAD`.
    *   If `BOSS_SPIRIT_DEAD` is "1" (meaning the Boss Spirit is dead), a special event occurs.

*   **Special Explosion:**
    *   When the Boss Spirit is dead and this script's `death` function is called, an explosion entity (`data/entities/projectiles/explosion.xml`) is spawned at the dying entity's location.
    *   This implies a unique visual or gameplay effect tied to the death of helpless entities after a major boss has been defeated.

## Global Variables Used

*   `HELPLESS_KILLS`: Tracks the number of times this death script has been triggered.
*   `BOSS_SPIRIT_DEAD`: A flag indicating whether the Boss Spirit has been defeated.

## Example Usage (Conceptual)

This script would typically be attached to entities that are considered "helpless" and whose deaths should contribute to the `HELPLESS_KILLS` counter. The specific entities that use this script would determine the context of "helplessness."

```lua
-- Example of how this script might be attached to an entity in its .xml file:
-- <entity name="some_helpless_creature">
--     ...
--     <script name="data/scripts/animals/helpless_death.lua" />
--     ...
-- </entity>
```