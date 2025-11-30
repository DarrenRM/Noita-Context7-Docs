---
title: Acid Projectile Transformation
category: scripts
---

---

# Acid Projectile Transformation

This script modifies existing projectiles in Noita, transforming them into acid-based projectiles under specific conditions. It iterates through all entities tagged as "projectile" and, if they do not already possess the "acid" tag, it converts them into a new acid projectile.

## Key Functionality

This script's primary purpose is to dynamically alter projectile behavior. It achieves this by:

### Projectile Identification and Filtering

-   **Iterates through all entities tagged as "projectile".**
-   **Filters out projectiles that already have the "acid" tag.** This ensures that only non-acid projectiles are affected.

### Projectile Modification

-   **Disables explosions on death and lifetime out.** For the identified projectiles, it explicitly sets `on_death_explode` and `on_lifetime_out_explode` to `"0"` within their `ProjectileComponent`.
-   **Retrieves existing velocity.** It reads the current velocity (`mVelocity`) of the projectile using `VelocityComponent`.

### Transformation

-   **Spawns a new acid projectile.** It uses the `shoot_projectile_from_projectile` function to create a new projectile defined by `data/entities/projectiles/deck/acidburst.xml` at the original projectile's position and with its velocity.
-   **Kills the original projectile.** The original, non-acid projectile is then destroyed using `EntityKill`.

## Core Components Involved

-   **`ProjectileComponent`**: Used to control explosion behaviors.
-   **`VelocityComponent`**: Used to read and transfer projectile velocity.
-   **`shoot_projectile_from_projectile`**: A utility function for spawning new projectiles based on existing ones.
-   **`EntityKill`**: Function to destroy entities.

## Example Usage Scenario

Imagine a scenario where a player fires a standard projectile. If this script is active, and the projectile doesn't have an "acid" tag, it will be intercepted. Instead of its default behavior, it will be replaced mid-flight by an "acidburst" projectile, effectively changing its damage type and effects.