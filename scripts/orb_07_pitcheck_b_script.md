---
title: Orb 07 Pitcheck B Script
category: scripts
---

# Orb 07 Pitcheck B Script

This script defines the behavior for a specific entity, likely an "orb" or trigger, that checks for the presence of a "boss pit" entity. When a non-invisible entity collides with this orb, it triggers the spawning of a `boss_pit.xml` entity and applies a force to it. The orb itself is then destroyed.

## Key Functionality

### `collision_trigger( colliding_entity )`

This function is executed when another entity collides with the entity associated with this script.

*   **`colliding_entity`**: The ID of the entity that triggered the collision.
*   **Logic**:
    *   Retrieves the ID and transform (position) of the current entity.
    *   Checks if the `colliding_entity` is invisible. If so, the function returns without further action.
    *   If the `colliding_entity` is not invisible, it proceeds to spawn a `boss_pit.xml` entity.
    *   The `boss_pit.xml` entity is spawned at a position relative to the orb's position (`x - 160`, `y + 256`).
    *   A downward force (`0, -80`) is applied to the newly spawned boss pit entity.
    *   The current orb entity is then destroyed using `EntityKill()`.

## Key Attributes/Elements

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions, likely for common game logic.
*   **`IsInvisible( colliding_entity )`**: A crucial check to prevent unintended triggers from invisible entities.
*   **`EntityLoad( "data/entities/animals/boss_pit/boss_pit.xml", x - 160, y + 256 )`**: The core spawning mechanism for the boss pit.
*   **`PhysicsApplyForce( pid, 0, -80 )`**: Applies a force to the spawned entity, influencing its movement.
*   **`EntityKill( entity_id )`**: Self-destruction of the orb after its task is complete.