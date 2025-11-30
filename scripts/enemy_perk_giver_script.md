---
title: Enemy Perk Giver Script
category: scripts
---

# Enemy Perk Giver Script

This script is designed to be attached to an entity that will randomly grant a perk to a nearby "mortal" enemy. It prioritizes enemies that are not specific boss types (Worms, Dragons, Ghosts, Lukki).

## Core Functionality

The script identifies a random, eligible perk from `perk_list.lua` and applies it to a chosen enemy.

### Key Components:

*   **Target Selection:**
    *   Searches for entities with the tag "mortal" within a 40-unit radius.
    *   Selects the first found target.
*   **Enemy Type Exclusion:**
    *   Checks if the target is a Worm, Dragon, Ghost, or Lukki. If it is, no perk is given.
*   **Perk Eligibility:**
    *   Iterates through `perk_list.lua`.
    *   Filters for perks where `usable_by_enemies` is `true`.
*   **Perk Application:**
    *   Randomly selects an eligible perk.
    *   Uses the `give_perk_to_enemy` function to apply the perk.
*   **Self-Destruction:**
    *   The entity executing this script is killed after its task is complete.

### Important Functions Used:

*   `GetUpdatedEntityID()`: Retrieves the ID of the entity running the script.
*   `EntityGetTransform()`: Gets the position of an entity.
*   `EntityGetInRadiusWithTag()`: Finds entities within a radius that have a specific tag.
*   `EntityGetComponent()`: Retrieves a specific component from an entity.
*   `SetRandomSeed()`: Initializes the random number generator based on entity position.
*   `Random()`: Generates a random number within a range.
*   `table.insert()`: Adds an element to a table.
*   `give_perk_to_enemy()`: (Assumed external function) Applies a perk to a target entity.
*   `EntityKill()`: Destroys an entity.

### Data Dependencies:

*   `data/scripts/game_helpers.lua`
*   `data/scripts/lib/utilities.lua`
*   `data/scripts/perks/perk_list.lua`

### Example `perk_list.lua` Entry (for context):

```lua
-- Example entry in perk_list.lua
{
    id = "PERK_SOMETHING_USEFUL",
    name = "Something Useful",
    description = "Grants a beneficial effect.",
    usable_by_enemies = true, -- This is the key attribute for this script
    -- ... other perk properties
},
{
    id = "PERK_PLAYER_ONLY",
    name = "Player Only Perk",
    description = "Only for the player.",
    usable_by_enemies = false, -- This perk would be skipped
    -- ... other perk properties
}
```