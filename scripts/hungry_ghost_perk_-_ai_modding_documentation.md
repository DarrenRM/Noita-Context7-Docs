---
title: Hungry Ghost Perk - AI Modding Documentation
category: scripts
---

---

# Hungry Ghost Perk

This document outlines the functionality of the "Hungry Ghost" perk, designed for AI-assisted modding in Noita. This perk allows the player to consume incoming projectiles under specific conditions.

## Core Functionality

The Hungry Ghost perk operates by periodically scanning for nearby projectiles. If a projectile not fired by the player is detected, it is consumed, and a visual effect is triggered.

### Key Attributes and Behaviors

*   **Projectile Consumption:** The perk targets projectiles within a radius of 12 units around the player.
*   **Player Projectile Exclusion:** Projectiles fired by the player are ignored.
*   **Visual Feedback:** Upon successful consumption, a "poof" particle effect and a small damage-boosting effect are spawned at the projectile's location.
*   **Cooldown Mechanism:** The perk utilizes a LuaComponent with a `execute_every_n_frame` attribute to manage its activation frequency.

### Technical Implementation Details

The perk's logic is primarily handled by a Lua script that interacts with Noita's entity and component system.

#### LuaComponent (`hungry_ghost_cooldown`)

This component controls the timing and execution of the perk's logic.

*   **`execute_every_n_frame`**:
    *   When set to `1`, the script actively scans for projectiles.
    *   When set to `160`, the script enters a cooldown period after consuming a projectile. This value dictates the delay before the perk can scan again.

#### Entity Interactions

*   **`EntityGetRootEntity( entity_id )`**: Retrieves the player's root entity ID.
*   **`EntityGetTransform( entity_id )`**: Gets the position (x, y) of an entity.
*   **`EntityGetInRadiusWithTag( x, y, radius, tag )`**: Finds entities within a specified radius and with a given tag. Used here to find "projectile" entities.
*   **`EntityGetComponent( entity_id, component_type )`**: Retrieves components of a specific type from an entity. Used to get `ProjectileComponent`.
*   **`ComponentGetValue2( component, value_name )`**: Reads a value from a component. Used to get `mWhoShot` and `execute_every_n_frame`.
*   **`ComponentSetValue2( component, value_name, value )`**: Sets a value on a component. Used to disable projectile explosions and manage the cooldown timing.
*   **`EntityLoad( xml_path, x, y )`**: Loads an entity from an XML file at a given position. Used to spawn particle and effect entities.
*   **`EntityAddChild( parent_id, child_id )`**: Makes one entity a child of another. Used to attach the effect entity to the player.
*   **`EntityKill( entity_id )`**: Destroys an entity. Used to remove the consumed projectile.

#### Key Logic Flow

1.  The script checks the `execute_every_n_frame` value of the `hungry_ghost_cooldown` LuaComponent.
2.  If `timing == 1` (active scan):
    *   It searches for nearby projectiles tagged "projectile".
    *   For each projectile, it checks if `mWhoShot` is *not* the player's ID.
    *   If a valid projectile is found:
        *   It disables `on_death_explode` and `on_lifetime_out_explode` on the projectile's `ProjectileComponent`.
        *   It spawns `data/entities/particles/poof_yellow_tiny.xml` and `data/entities/misc/effect_damage_plus_small.xml` at the projectile's location.
        *   The effect entity is added as a child to the player.
        *   The projectile is killed.
        *   The `execute_every_n_frame` is set to `160` to initiate cooldown.
3.  If `timing ~= 1` (cooldown):
    *   The `execute_every_n_frame` is reset to `1` to prepare for the next scan.

This documentation provides a foundational understanding for modders looking to integrate or modify the Hungry Ghost perk's behavior.