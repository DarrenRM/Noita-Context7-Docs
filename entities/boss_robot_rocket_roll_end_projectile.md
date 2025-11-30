---
title: Boss Robot Rocket Roll End Projectile
category: entities
---

# Boss Robot Rocket Roll End Projectile

This entity defines the projectile spawned by the Boss Robot's "rocket roll" attack. It's a simple Lua script that triggers the creation of a specific rocket projectile.

## Key Attributes

*   **`entity_id`**: A unique identifier for the entity, obtained dynamically.
*   **`x`, `y`**: The coordinates where the projectile is spawned.

## Core Functionality

The primary function of this script is to initiate the firing of a rocket projectile.

### `shoot_projectile_from_projectile`

This function is called to create a new projectile.

*   **`entity_id`**: The ID of the entity that is firing this projectile (in this case, the "rocket roll end" entity itself).
*   **`"data/entities/animals/boss_robot/rocket.xml"`**: The path to the XML file defining the actual rocket projectile to be spawned.
*   **`x`, `y`**: The spawn coordinates for the new rocket projectile.
*   **`0`, `0`**: These likely represent the initial velocity components (vx, vy) of the spawned projectile. In this case, it's set to zero, implying the rocket's movement is defined within its own XML.