---
title: Teleport Projectile Closer Hit Logic
category: scripts
---

# Teleport Projectile Closer Hit Logic

This script defines the behavior of a projectile that, upon hitting an entity, teleports that entity to a stored origin point.

## Core Functionality

The primary purpose of this script is to:
1.  Identify the entity that fired the "teleport_projectile_closer" projectile.
2.  Retrieve the stored origin coordinates (x, y) associated with that projectile.
3.  Teleport the hit enemy entity to these stored origin coordinates.

## Key Components and Logic

### Entity Identification and Proximity Check

*   `GetUpdatedEntityID()`: Retrieves the unique ID of the current projectile entity.
*   `EntityGetRootEntity(entity_id)`: Gets the ID of the root entity that spawned this projectile (likely the enemy that fired it).
*   `EntityGetInRadiusWithTag(x, y, 32, "teleport_projectile_closer")`: Searches for entities within a 32-unit radius that have the tag "teleport_projectile_closer". This is how the script finds the originating projectile.

### Storing and Retrieving Origin Coordinates

*   `EntityGetComponent(pid, "VariableStorageComponent", "teleport_closer")`: Accesses the `VariableStorageComponent` of the identified projectile, specifically looking for variables named "teleport_closer".
*   The script iterates through the components to find `name` attributes that are "origin\_x" and "origin\_y".
*   `ComponentGetValue2(v, "value_float")`: Extracts the float value associated with the "origin\_x" and "origin\_y" variables.

### Teleportation

*   `EntitySetTransform(enemy_id, ox, oy)`: Sets the absolute transform (position) of the hit enemy entity to the retrieved origin coordinates.
*   `EntityApplyTransform(enemy_id, ox, oy)`: Applies the transform, ensuring the entity's position is updated correctly.

## Script Flow

1.  The script starts by getting the current projectile's ID and its root entity's ID.
2.  It then searches for a projectile with the tag "teleport\_projectile\_closer" in its vicinity.
3.  If such a projectile is found, the script attempts to retrieve its stored origin X and Y coordinates from a `VariableStorageComponent`.
4.  If both origin X and Y coordinates are successfully retrieved, the hit enemy entity is teleported to those coordinates.
5.  The commented-out `EntityKill(entity_id)` suggests that the projectile itself might be intended to be destroyed after its effect, but this functionality is currently inactive.