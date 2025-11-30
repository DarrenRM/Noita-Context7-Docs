---
title: Damaged Physics Lantern Script
category: scripts
---

# Damaged Physics Lantern Script

This script defines the behavior of a damaged physics lantern entity in Noita. When the lantern is destroyed, it spawns a `fire.xml` entity at its location.

## Core Functionality

### `physics_body_modified( is_destroyed )`

This function is called when the physics body of the entity is modified, specifically when it is destroyed.

*   **`is_destroyed`**: A boolean indicating whether the entity has been destroyed.

#### Key Actions:

1.  **Get Entity ID**: Retrieves the ID of the entity that triggered the modification.
2.  **Get Position**: Obtains the X and Y coordinates of the entity's transform.
3.  **Spawn Fire**: Loads and spawns the `data/entities/misc/fire.xml` entity at the lantern's position.