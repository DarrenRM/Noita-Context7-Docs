---
title: Giga Discs Effect Script
category: scripts
---

# Giga Discs Effect Script

This script modifies existing projectiles, specifically those tagged with "projectile", to transform them into larger "disc_bullet_big" projectiles. It ensures that the original projectiles do not explode on death or when their lifetime ends, and then spawns a new, larger disc projectile at the original projectile's location and velocity.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile, it checks if it's already a "disc_bullet_big". If not, it proceeds to:

1.  **Disable Explosions:** Prevents the original projectile from exploding on death or lifetime expiry.
2.  **Capture Velocity:** Records the current velocity of the original projectile.
3.  **Spawn Giga Disc:** Shoots a new "disc_bullet_big" projectile from the original projectile's position and with its captured velocity.
4.  **Kill Original:** Destroys the original projectile.

## Key Components and Attributes

### Entity Processing

*   `GetUpdatedEntityID()`: Retrieves the ID of the entity currently being processed by the script.
*   `EntityGetTransform( entity_id )`: Gets the position (x, y) of an entity.
*   `EntityGetWithTag( "projectile" )`: Retrieves a list of all entity IDs that have the tag "projectile".
*   `EntityGetTags( projectile_id )`: Retrieves the tags associated with a specific projectile entity.
*   `string.find( tags, "disc_bullet_big" )`: Checks if the "disc_bullet_big" tag exists within the projectile's tags.
*   `EntityGetComponent( projectile_id, "ProjectileComponent" )`: Retrieves all `ProjectileComponent` components for an entity.
*   `ComponentSetValue( comp_id, "on_death_explode", "0" )`: Sets the `on_death_explode` property of a `ProjectileComponent` to "0" (false), disabling explosion on death.
*   `ComponentSetValue( comp_id, "on_lifetime_out_explode", "0" )`: Sets the `on_lifetime_out_explode` property of a `ProjectileComponent` to "0" (false), disabling explosion when lifetime expires.
*   `EntityGetComponent( projectile_id, "VelocityComponent" )`: Retrieves all `VelocityComponent` components for an entity.
*   `edit_component( projectile_id, "VelocityComponent", function(comp,vars) ... end )`: A utility to safely edit a `VelocityComponent`.
*   `ComponentGetValueVector2( comp, "mVelocity", vel_x, vel_y)`: Retrieves the velocity vector (vel_x, vel_y) from a `VelocityComponent`.
*   `shoot_projectile_from_projectile( projectile_id, "data/entities/projectiles/deck/disc_bullet_big.xml", px, py, vel_x, vel_y )`: Spawns a new projectile.
    *   `projectile_id`: The entity ID to spawn from (used for position/velocity reference).
    *   `"data/entities/projectiles/deck/disc_bullet_big.xml"`: The XML file defining the projectile to spawn.
    *   `px, py`: The spawn position.
    *   `vel_x, vel_y`: The spawn velocity.
*   `EntityKill( projectile_id )`: Destroys the specified entity.

### Logic Flow

The script uses a conditional `if ( #projectiles > 0 ) then` to ensure it only runs if there are any projectiles present. The `for i,projectile_id in ipairs( projectiles ) do` loop iterates through each found projectile. The inner `if ( tags == nil ) or ( string.find( tags, "disc_bullet_big" ) == nil ) then` acts as a filter, ensuring that only projectiles *not* already tagged as "disc_bullet_big" are processed.