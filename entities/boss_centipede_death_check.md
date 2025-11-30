---
title: Boss Centipede Death Check
category: entities
---

# Boss Centipede Death Check

This script defines the behavior when the boss centipede entity is destroyed. It checks for the presence of specific "seed" entities within a radius and applies a game flag if found.

## `death()` Function

This function is called when the boss centipede entity is marked for death.

### Key Actions:

1.  **Get Entity Information:**
    *   Retrieves the `entity_id` of the entity being updated.
    *   Gets the `x` and `y` coordinates of the entity's transform.

2.  **Check for Nearby "Seeds":**
    *   Searches for entities with the tag `"seed_e"` within a radius of 540 units around the centipede.
    *   Searches for entities with the tag `"seed_f"` within a radius of 540 units around the centipede.

3.  **Apply Game Flag:**
    *   If either `sun` (entities with `"seed_e"`) or `sun2` (entities with `"seed_f"`) are found (i.e., the count of found entities is greater than 0), the following occurs:
        *   The message `"SUN DETECTED"` is printed to the console.
        *   The game flag `"sun_kill"` is added. This flag likely signifies a specific death condition or consequence.

### Relevant Variables:

*   `entity_id`: The unique identifier for the boss centipede entity.
*   `x`, `y`: The world coordinates of the boss centipede.
*   `sun`: A table containing entities with the tag `"seed_e"` found within the radius.
*   `sun2`: A table containing entities with the tag `"seed_f"` found within the radius.

### Dependencies:

*   `dofile_once( "data/scripts/lib/utilities.lua" )`: Imports utility functions, likely including `GetUpdatedEntityID()`, `EntityGetTransform()`, `EntityGetInRadiusWithTag()`, and `GameAddFlagRun()`.