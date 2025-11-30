---
title: Slow Projectiles Effect
category: scripts
---

# Slow Projectiles Effect

This script creates an effect that slows down all projectiles currently in the game. It achieves this by iterating through all entities tagged as "projectile" and reducing their velocity.

## Key Functionality

*   **Targeting Projectiles:** Identifies all entities with the tag "projectile".
*   **Velocity Modification:** Accesses and modifies the `VelocityComponent` of each projectile.
*   **Speed Reduction:** Decreases the `mVelocity` of projectiles by 15% (multiplies by 0.85).

## Technical Details

### Script Logic

The script performs the following steps:

1.  **Initialization:**
    *   Includes `utilities.lua` for helper functions.
    *   Gets the `entity_id` of the entity running this script.
    *   Retrieves the `x` and `y` coordinates of the script's entity.
2.  **Projectile Search:**
    *   Uses `EntityGetWithTag("projectile")` to get a list of all projectile entity IDs.
3.  **Velocity Adjustment Loop:**
    *   Checks if any projectiles were found (`#projectiles > 0`).
    *   Iterates through each `projectile_id` in the `projectiles` list.
    *   For each projectile:
        *   Retrieves the `VelocityComponent` using `EntityGetComponent`.
        *   If the `VelocityComponent` exists:
            *   Uses `edit_component` to safely modify the component.
            *   Reads the current `mVelocity` vector.
            *   Multiplies both `vel_x` and `vel_y` by `0.85` to reduce speed.
            *   Writes the modified `mVelocity` back to the component.

### Relevant Components

*   **`VelocityComponent`**: This component is essential for controlling the movement of entities. The script directly manipulates its `mVelocity` property.

### Example Usage (Conceptual)

This script would typically be attached to an entity that triggers a global effect, such as a spell or an environmental hazard. For instance, a "Slow Field" spell might spawn an entity with this script attached, causing all projectiles within its radius (or globally, depending on implementation) to slow down.

```lua
-- Conceptual example of how this script might be triggered
-- This is NOT part of the effect_slow_bullets.lua script itself

local spell_entity_id = EntitySpawn("data/entities/spells/slow_field.xml", x, y)
-- Assuming slow_field.xml has a component that runs effect_slow_bullets.lua
```