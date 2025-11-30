---
title: Tiny Explosion Projectile Configuration
category: scripts
---

# Tiny Explosion Projectile Configuration

This script modifies the `explosion_radius` of a projectile to be a small value, effectively creating a "tiny" explosion. It targets projectiles that have `ProjectileComponent`, `ExplosionComponent`, or `ExplodeOnDamageComponent`.

## Key Attributes Modified

The primary attribute being adjusted is `explosion_radius` within the `config_explosion` table of relevant components.

### `ProjectileComponent`

This component is often present on entities that are projectiles.

*   **`config_explosion.explosion_radius`**: Set to `"5"`. This determines the radius of the explosion effect when the projectile hits something or detonates.

### `ExplosionComponent`

This component directly handles explosion logic.

*   **`config_explosion.explosion_radius`**: Set to `"5"`. This reinforces the explosion radius for entities that explicitly use this component for their explosive behavior.

### `ExplodeOnDamageComponent`

This component triggers an explosion when the entity takes damage.

*   **`config_explosion.explosion_radius`**: Set to `"5"`. This ensures that when an entity with this component explodes due to damage, the explosion's radius is small.

## Lua Script Logic

The script performs the following actions:

1.  **Get Entity ID and Transform**: Retrieves the current entity's ID and its position.
2.  **Get Root Entity**: Identifies the root entity, which is often the projectile itself.
3.  **Conditional Modification**: If a valid root entity is found:
    *   It attempts to edit the `ProjectileComponent` to set the `explosion_radius` to "5".
    *   It then iterates through all `ExplosionComponent` instances on the entity and sets their `explosion_radius` to "5".
    *   Finally, it iterates through all `ExplodeOnDamageComponent` instances and sets their `explosion_radius` to "5".

This ensures that regardless of which component is primarily responsible for the explosion, the radius is consistently set to a small value.