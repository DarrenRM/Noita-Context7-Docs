---
title: Hook Projectile Behavior
category: scripts
---

# Hook Projectile Behavior

This script defines the behavior of a "hook" projectile in Noita. When fired, it attempts to attach to its owner and pull them towards the projectile's current location.

## Key Components and Logic

### Projectile Initialization

*   **`dofile_once("data/scripts/lib/utilities.lua")`**: Imports utility functions.
*   **`GetUpdatedEntityID()`**: Retrieves the unique ID of the projectile entity.
*   **`EntityGetTransform( entity_id )`**: Gets the position (`x`, `y`) and rotation (`rot`) of the projectile.
*   **`EntityGetFirstComponent( entity_id, "ProjectileComponent" )`**: Finds the projectile's core component to identify its owner.
*   **`ComponentGetValue2( comp, "mWhoShot" )`**: Retrieves the entity ID of the projectile's owner.

### Owner Interaction and Velocity Manipulation

*   **Owner Check**: The script proceeds only if a valid `owner_id` is found.
*   **Direction Calculation**:
    *   `EntityGetTransform( owner_id )`: Gets the owner's position.
    *   `math.atan2( y - py, x - px )`: Calculates the angle between the owner and the projectile.
    *   `dir = 0 - ...`: Determines the direction to pull the owner.
*   **Velocity Calculation**:
    *   `vel_x = math.cos( dir ) * 800`
    *   `vel_y = 0 - math.sin( dir ) * 800`
    *   These lines calculate the velocity vector needed to move the owner towards the projectile. The magnitude is set to 800.
*   **Applying Velocity**:
    *   **`edit_component( owner_id, "VelocityComponent", function(vcomp,vars) ... end)`**: Modifies the `VelocityComponent` of the owner.
        *   **`ComponentSetValueVector2( vcomp, "mVelocity", vel_x, vel_y )`**: Sets the owner's velocity to the calculated `vel_x` and `vel_y`.
    *   **`edit_component( owner_id, "CharacterDataComponent", function(ccomp,vars) ... end)`**: Modifies the `CharacterDataComponent` of the owner.
        *   **`ComponentSetValueVector2( ccomp, "mVelocity", vel_x, vel_y )`**: Also sets the owner's velocity via the `CharacterDataComponent`, ensuring the pull effect.

## Key Attributes Highlighted

*   **`mWhoShot`**: Identifies the entity that fired the projectile.
*   **`mVelocity`**: The velocity vector applied to the owner to simulate the pulling effect.
*   **Magnitude of Velocity**: The constant `800` dictates the strength of the pull.

## Summary

This script is a straightforward implementation of a grappling hook mechanic. It identifies the projectile's owner and then applies a significant velocity to that owner, directed towards the projectile's current position, effectively pulling the owner.