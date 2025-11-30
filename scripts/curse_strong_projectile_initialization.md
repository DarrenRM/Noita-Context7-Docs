---
title: Curse Strong Projectile Initialization
category: scripts
---

# Curse Strong Projectile Initialization

This script handles the initialization and stacking logic for the "strong curse" effect in Noita. It determines whether to apply a new curse or refresh an existing one.

## Core Logic

The script checks for the presence of the `effect_CURSE` tag on the root entity.

-   **If `effect_CURSE` is NOT present:**
    -   A new `curse_strong.xml` entity is loaded at the current position.
    -   This new entity is added as a child to the root entity.
    -   The `effect_CURSE` tag is added to the root entity.
-   **If `effect_CURSE` IS present:**
    -   The script iterates through all child entities of the root.
    -   It searches for a child entity with the `effect_CURSE` tag.
    -   If found, it refreshes the `LifetimeComponent` and increases the damage stored in a `VariableStorageComponent`.

Finally, the projectile entity that triggered this script is killed.

## Key Components and Attributes

### Entity Loading and Tagging

-   `EntityLoad( "data/entities/misc/curse_strong.xml", x, y )`: Loads the `curse_strong.xml` entity.
-   `EntityAddChild( root_id, eid )`: Attaches the loaded entity as a child.
-   `EntityAddTag( root_id, "effect_CURSE" )`: Applies the curse tag to the root entity.
-   `EntityHasTag( root_id, "effect_CURSE" )`: Checks for the presence of the curse tag.

### Lifetime and Damage Management (when curse exists)

-   `EntityGetAllChildren( root_id )`: Retrieves all child entities of the root.
-   `EntityGetFirstComponent( v, "LifetimeComponent", "effect_curse_lifetime" )`: Gets the `LifetimeComponent` associated with the curse.
    -   `ComponentSetValue2( comp, "creation_frame", GameGetFrameNum() )`: Resets the creation frame to the current game frame.
    -   `ComponentSetValue2( comp, "kill_frame", GameGetFrameNum() + 300 )`: Sets the kill frame 300 frames into the future.
-   `EntityGetFirstComponent( v, "VariableStorageComponent", "effect_curse_damage" )`: Gets the `VariableStorageComponent` storing curse damage.
    -   `ComponentGetValue2( comp, "value_float" )`: Retrieves the current float value of the damage.
    -   `ComponentSetValue2( comp, "value_float", damage )`: Updates the damage value (incremented by 0.08).

### Entity Management

-   `GetUpdatedEntityID()`: Gets the ID of the entity being updated.
-   `EntityGetRootEntity( entity_id )`: Gets the root entity of a given entity.
-   `EntityGetTransform( root_id )`: Gets the transform (position) of an entity.
-   `EntityKill( entity_id )`: Destroys the specified entity.