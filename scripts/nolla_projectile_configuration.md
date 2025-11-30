---
title: Nolla Projectile Configuration
category: scripts
---

# Nolla Projectile Configuration

This script configures the behavior of a "Nolla" projectile, primarily focusing on its lifespan.

## Core Functionality

The script targets a projectile entity and modifies its `ProjectileComponent` and `LifetimeComponent` to set a very short lifespan.

### Key Attributes Modified

*   **`ProjectileComponent.lifetime`**: Set to `1`. This likely controls the projectile's active duration before it's automatically removed.
*   **`LifetimeComponent.lifetime`**: Set to `1`. This component also governs the entity's lifespan, ensuring it's removed quickly.

## Script Logic

1.  **Initialization**:
    *   `dofile_once("data/scripts/lib/utilities.lua")`: Includes utility functions.
    *   `local entity_id = GetUpdatedEntityID()`: Retrieves the ID of the current entity being processed.
    *   `local x, y = EntityGetTransform( entity_id )`: Gets the position of the entity (though `x` and `y` are not used in this specific script).
    *   `entity_id = EntityGetRootEntity( entity_id )`: Gets the root entity of the projectile, which is often the main entity to modify.

2.  **Conditional Modification**:
    *   `if ( entity_id ~= NULL_ENTITY ) then ... end`: Ensures that the script only proceeds if a valid root entity was found.

3.  **Component Editing**:
    *   `edit_component( entity_id, "ProjectileComponent", function(comp,vars) ... end)`: Accesses and modifies the `ProjectileComponent`.
        *   `ComponentSetValue( comp, "lifetime", 1 )`: Sets the `lifetime` property of the `ProjectileComponent` to `1`.
    *   `edit_component( entity_id, "LifetimeComponent", function(comp,vars) ... end)`: Accesses and modifies the `LifetimeComponent`.
        *   `ComponentSetValue( comp, "lifetime", 1 )`: Sets the `lifetime` property of the `LifetimeComponent` to `1`.

## Summary

This script is a straightforward example of how to programmatically control the lifespan of a projectile in Noita, making it disappear almost immediately after creation.