---
title: Mimic Damage Behavior
category: scripts
---

# Mimic Damage Behavior

This script defines the behavior of a Mimic entity when it receives damage.

## Key Functionality

The primary function `damage_received` is triggered when the Mimic takes damage.

### `damage_received( damage, desc, entity_who_caused, is_fatal )`

*   **Purpose**: Handles the logic executed when the Mimic entity is damaged.
*   **Parameters**:
    *   `damage`: The amount of damage received.
    *   `desc`: A description of the damage source.
    *   `entity_who_caused`: The entity ID that caused the damage.
    *   `is_fatal`: A boolean indicating if the damage is fatal.
*   **Core Logic**:
    *   Prevents self-damage.
    *   Sets a random seed based on game frame and entity position for deterministic randomness.
    *   With a 1 in 16 chance (`Random(0,15) == 1`), it spawns a `longleg.xml` entity near the Mimic.
    *   The spawned `longleg` entity is given a random velocity, primarily pushing it upwards and slightly horizontally.

## Spawning Behavior

When the damage condition is met, a `longleg` entity is spawned.

### `EntityLoad( "data/entities/animals/longleg.xml", pos_x + math.random(-10, 10), pos_y + math.random(-10, 10))`

*   **Action**: Loads the `longleg.xml` entity.
*   **Positioning**: Spawns the `longleg` at a random offset (±10 units) from the Mimic's current position.

### Velocity Modification

The spawned `longleg` receives a randomized velocity.

```lua
edit_component( e, "VelocityComponent", function(comp,vars)
	local vel_x = Random(-90,90)
	local vel_y = Random(-150,0)
	ComponentSetValueVector2( comp, "mVelocity", vel_x, vel_y )
end)
```

*   **Target Component**: `VelocityComponent` of the spawned entity.
*   **`vel_x`**: Random horizontal velocity between -90 and 90.
*   **`vel_y`**: Random vertical velocity between -150 (upwards) and 0.