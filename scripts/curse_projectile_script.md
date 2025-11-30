---
title: Curse Projectile Script
category: scripts
---

# Curse Projectile Script

This script defines the behavior of a curse projectile in Noita. When a curse projectile hits an entity, it inflicts a small amount of curse damage.

## Key Attributes

*   **`damage`**: The base amount of curse damage inflicted. This can be modified by `VariableStorageComponent`.
*   **`who_shot`**: Stores the entity ID of the projectile's shooter, used for damage attribution.

## Logic Breakdown

1.  **Initialization**:
    *   Retrieves the current entity ID and its root entity ID.
    *   Initializes `who_shot` to the projectile's own entity ID.

2.  **Curse Check**:
    *   Checks if the projectile has the `curse_NOT` tag. If it does, the curse effect is skipped.

3.  **Damage and Shooter Retrieval**:
    *   Sets a default `damage` value of `0.08`.
    *   Iterates through `VariableStorageComponent`s attached to the projectile.
    *   If a component named `effect_curse_damage` is found, its `value_float` is used to update the `damage`.
    *   If a component named `projectile_who_shot` is found, its `value_int` is used to update `who_shot`.

4.  **Damage Infliction**:
    *   Calls `EntityInflictDamage` on the `root_id` (the entity hit by the projectile).
    *   The damage type is set to `DAMAGE_CURSE`.
    *   Includes a hit effect identifier (`$damage_hitfx_curse`) and a damage type (`DISINTEGRATED`).
    *   Passes the `who_shot` entity ID for attribution.

```lua
-- Example of how VariableStorageComponent might be used to modify curse damage
-- This would typically be set on the wand or spell that creates the curse projectile.

-- Assuming a VariableStorageComponent is added to the projectile entity:
-- ComponentAdd( projectile_entity_id, "VariableStorageComponent", {
--     value_float = 0.15,
--     name = "effect_curse_damage",
-- } )

-- Assuming a VariableStorageComponent is added to the projectile entity to specify the shooter:
-- ComponentAdd( projectile_entity_id, "VariableStorageComponent", {
--     value_int = shooter_entity_id,
--     name = "projectile_who_shot",
-- } )
```