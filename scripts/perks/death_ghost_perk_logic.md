---
title: Death Ghost Perk Logic
category: scripts/perks
---

# Death Ghost Perk Logic

This script handles the logic for the "Death Ghost" perk in Noita. When a player with this perk dies, it applies a "death_ghost" tag to nearby entities that are not already ghosts or polymorphed. This tag likely triggers a secondary script (`death_ghost_death.lua`) to handle the actual ghost transformation or behavior.

## Key Functionality

*   **Proximity Detection:** Identifies entities within a 160-unit radius of the player's death location.
*   **Tagging:** Applies the `"death_ghost"` tag to eligible nearby entities.
*   **Exclusion:** Avoids tagging entities that already possess the `"death_ghost"` tag or the `"polymorphed"` tag.
*   **Component Addition:** Adds a `LuaComponent` to the tagged entities, specifying a `script_death` to be executed upon their own death.

## Core Logic Breakdown

The script iterates through entities found within a specified radius. For each entity, it checks if it meets the criteria for becoming a "death ghost":

1.  **Is it a homing target?** The script specifically looks for entities with the `"homing_target"` tag. This suggests that the Death Ghost perk might interact with or affect entities that are already designated as targets for other effects.
2.  **Does it already have the "death_ghost" tag?** If the entity is already a death ghost, it's skipped to prevent redundant processing.
3.  **Is it polymorphed?** Entities that are already polymorphed are also excluded.

If an entity passes these checks, the script performs the following actions:

*   **Adds the "death_ghost" tag:** This marks the entity for further processing.
*   **Adds a LuaComponent:** This component is crucial for defining what happens when the newly tagged entity eventually dies.
    *   `script_death = "data/scripts/perks/death_ghost_death.lua"`: This specifies the script that will be executed when the entity dies. This is where the actual "ghost" behavior is likely implemented.
    *   `execute_every_n_frame = "-1"`: This setting indicates that the `script_death` should only be executed once, upon the entity's death, rather than continuously.

## Relevant Attributes and Values

| Attribute              | Value                                      | Description