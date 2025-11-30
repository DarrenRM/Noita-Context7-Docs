---
title: Piercing Shot Projectile Modification
category: scripts
---

# Piercing Shot Projectile Modification

This script modifies the behavior of a projectile, specifically targeting its `ProjectileComponent` to alter its collision behavior.

## Key Functionality

The primary purpose of this script is to ensure that a projectile, when it collides with something, does not immediately die. This is achieved by setting the `on_collision_die` property of the `ProjectileComponent` to `0`.

## Technical Details

### Entity Identification

-   `entity_id`: Retrieves the unique identifier for the current entity.
-   `x`, `y`: Gets the transform (position) of the current entity.
-   `parent_id`: Identifies the parent entity of the current projectile. This is crucial for determining which entity's components to modify.

### Target Entity Determination

The script first checks if the projectile has a parent.
-   If a `parent_id` exists (meaning the projectile was spawned by another entity), the `target_id` is set to the `parent_id`.
-   If no `parent_id` is found, the `target_id` defaults to the `entity_id` itself.

### Component Modification

-   The script attempts to retrieve the `ProjectileComponent` from the `target_id`.
-   If the component is found and exists, the `edit_component` function is used to modify it.
-   Specifically, the `on_collision_die` property within the `ProjectileComponent` is set to `0`.

```lua
-- Example of the relevant component modification:
edit_component( target_id, "ProjectileComponent", function(comp,vars)
	vars.on_collision_die = 0
end)
```

## Impact

By setting `on_collision_die` to `0`, this script effectively makes the projectile "pierce" through whatever it hits, rather than being destroyed upon the first collision. This is a common mechanic for projectiles designed to pass through multiple targets or obstacles.