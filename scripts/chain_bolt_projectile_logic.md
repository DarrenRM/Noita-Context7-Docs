---
title: Chain Bolt Projectile Logic
category: scripts
---

# Chain Bolt Projectile Logic

This script defines the behavior of the "Chain Bolt" projectile in Noita. It's designed to "chain" to nearby targets, teleporting to them and then continuing its trajectory.

## Core Functionality

The primary function of this script is to:
1.  **Detect nearby targets:** It scans for entities with the "homing_target" tag within a specified radius.
2.  **Chain to a target:** If a valid target is found (one that hasn't been hit recently), the projectile teleports to that target's location.
3.  **Continue trajectory:** If no target is found, the projectile continues in its original direction, but with a slight offset.
4.  **Spawn an explosion:** After its movement logic, it spawns a "chain_bolt_explosion" projectile at its current location.

## Key Attributes and Logic

### Target Acquisition and Chaining

*   **`radius`**: Defines the search radius for potential targets.
    *   Value: `48`
*   **`default_teleport_radius`**: The distance the projectile moves if no target is found.
    *   Value: `30`
*   **`homing_target` tag**: Entities with this tag are considered valid targets for chaining.
*   **`prev_entity_id` and `prev_prev_entity_id`**: These variables are crucial for preventing the projectile from chaining back to the same entity it just hit or the one before that, creating a more dynamic chain. They are stored and retrieved using `VariableStorageComponent`.

### Movement Logic

*   **Targeted Movement**: If a target is found, the projectile's `EntitySetTransform` is updated to the target's hitbox center.
*   **Untargeted Movement**: If no target is found, the projectile moves based on its `angle` and `default_teleport_radius`.

### State Management

*   **`VariableStorageComponent`**: Used to store `prev_entity_id` and `prev_prev_entity_id` between frames, allowing the projectile to remember its recent targets.

### Projectile Spawning

*   **`shoot_projectile_from_projectile`**: This function is called at the end of the script to spawn a new projectile.
    *   **`entity_id`**: The ID of the current projectile.
    *   **`"data/entities/projectiles/deck/chain_bolt_explosion.xml"`**: The XML file defining the explosion projectile that is spawned.
    *   **`x`, `y`**: The coordinates where the explosion projectile is spawned.
    *   **`0`, `0`**: These likely represent initial velocity components, which are zero for the explosion.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity defined in an XML file. The XML would specify the projectile's visual appearance, damage, and other base properties, while this Lua script handles its unique chaining behavior.

```lua
-- Example of how this script might be referenced in a projectile's XML
-- (This is illustrative and not part of the provided Lua script)

-- <entity name="chain_bolt">
--   <property name="SpriteFile" value="data/projectiles/chain_bolt.png" />
--   <property name="ScriptFile" value="data/scripts/chain_bolt.lua" />
--   <property name="HomingEnabled" value="1" /> -- Might be a conceptual property
--   <property name="TargetTag" value="homing_target" /> -- Might be a conceptual property
--   <property name="ChainRadius" value="48" /> -- Might be a conceptual property
--   <components>
--     <VariableStorageComponent name="prev_entity_id" value_int="0" />
--     <VariableStorageComponent name="prev_prev_entity_id" value_int="0" />
--     <!-- Other components like DamageComponent, PhysicsComponent -->
--   </components>
-- </entity>
```