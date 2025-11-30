---
title: Tentacle Ray Projectile
category: scripts
---

# Tentacle Ray Projectile

This script defines the behavior for a projectile that spawns a "tentacle" entity.

## Core Functionality

The primary purpose of this script is to initiate the spawning of a `tentacle.xml` projectile.

### Key Attributes

*   **`entity_id`**: The unique identifier for the current entity (the projectile itself).
*   **`pos_x`, `pos_y`**: The current world coordinates of the projectile.
*   **`angle`**: A randomly generated angle (0-359 degrees) used to determine the direction of the spawned tentacle.
*   **`length`**: A fixed value (3000) that influences the initial velocity calculation.
*   **`vel_x`, `vel_y`**: Calculated velocity components for the spawned tentacle based on the `angle` and `length`.
*   **`proj_id`**: The entity ID of the newly spawned tentacle projectile.

### Spawning Mechanism

The `shoot_projectile_from_projectile` function is used to create the tentacle.

```lua
local proj_id = shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/tentacle.xml", pos_x, pos_y, vel_x, vel_y )
```

*   **`entity_id`**: The projectile that is currently executing this script.
*   **`"data/entities/projectiles/deck/tentacle.xml"`**: The XML file defining the tentacle entity to be spawned.
*   **`pos_x`, `pos_y`**: The spawn location of the tentacle.
*   **`vel_x`, `vel_y`**: The initial velocity of the spawned tentacle.

### Important Note

The script explicitly mentions that the `mWhoShot` component of the spawned tentacle will refer to the tentacle projectile itself, not the original entity that fired the initial projectile.