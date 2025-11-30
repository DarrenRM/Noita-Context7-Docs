---
title: Effect Giga Discs Projectile Spawner
category: scripts/
---

# Effect Giga Discs Projectile Spawner

This script is responsible for spawning "giga discs" from existing projectiles that do not already have the "disc_bullet_big" tag. It effectively transforms regular projectiles into larger, more powerful disc projectiles.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile that *doesn't* have the "disc_bullet_big" tag, it performs the following actions:

1.  **Retrieves Projectile Properties:** Gets the current position (`px`, `py`) and velocity (`vel_x`, `vel_y`) of the projectile.
2.  **Disables Default Explosions:** Modifies the `ProjectileComponent` to prevent the projectile from exploding on death or when its lifetime expires.
3.  **Spawns Giga Disc:** Uses the `shoot_projectile_from_projectile` function to create a new projectile defined by `data/entities/projectiles/deck/disc_bullet_big.xml` at the original projectile's position and with its velocity.
4.  **Kills Original Projectile:** Removes the original projectile from the game.

## Key Attributes & Elements

### `shoot_projectile_from_projectile` Function

This is the central function for spawning new projectiles based on existing ones.

*   **`projectile_id`**: The ID of the projectile to spawn *from*.
*   **`"data/entities/projectiles/deck/disc_bullet_big.xml"`**: The XML file defining the properties of the new projectile to be spawned. This is the "giga disc" definition.
*   **`px`, `py`**: The X and Y coordinates where the new projectile will be spawned.
*   **`vel_x`, `vel_y`**: The initial velocity components for the new projectile.

### `EntityGetWithTag("projectile")`

This function is used to retrieve all entities in the game that have the tag "projectile".

### `EntityGetTags(projectile_id)`

Retrieves the tags associated with a specific projectile entity. The script checks for the absence of the `"disc_bullet_big"` tag.

### `EntityGetComponent(projectile_id, "ProjectileComponent")`

Accesses the `ProjectileComponent` of a projectile. This component is modified to disable `on_death_explode` and `on_lifetime_out_explode`.

### `ComponentSetValue(comp_id, "attribute_name", "value")`

Used to set specific values for components. Here, it's used to set explosion-related attributes to `"0"` (false).

### `EntityKill(projectile_id)`

Terminates and removes a projectile entity from the game.