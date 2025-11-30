---
title: Blood Tentacle Projectile
category: scripts
---

# Blood Tentacle Projectile

This script defines the behavior for a projectile that spawns a "blood tentacle" entity.

## Core Functionality

The script's primary purpose is to:
*   Determine the projectile's spawn position and orientation.
*   Remove the projectile from its parent entity.
*   Launch a new `bloodtentacle.xml` projectile entity.

## Key Attributes

*   **`entity_id`**: The unique identifier for the current projectile entity.
*   **`root_id`**: The root entity of the projectile.
*   **`pos_x`, `pos_y`**: The current X and Y coordinates of the projectile.
*   **`angle`**: A randomly generated angle (0-359 degrees) used to determine the projectile's direction.
*   **`length`**: A fixed value (250) influencing the initial velocity calculation.
*   **`vel_x`, `vel_y`**: Calculated X and Y components of the projectile's velocity, based on the `angle` and `length`.
*   **`shoot_projectile()`**: The core function that instantiates the `bloodtentacle.xml` entity.

### `shoot_projectile()` Parameters

The `shoot_projectile` function is called with the following arguments:

| Parameter        | Type   | Description                                                              |
| :--------------- | :----- | :----------------------------------------------------------------------- |
| `entity_id`      | number | The ID of the entity to be shot (in this case, the blood tentacle itself). |
| `projectile_xml` | string | The path to the XML file defining the projectile's appearance and behavior. |
| `pos_x`          | number | The X coordinate where the projectile will be spawned.                   |
| `pos_y`          | number | The Y coordinate where the projectile will be spawned.                   |
| `vel_x`          | number | The initial X velocity of the projectile.                                |
| `vel_y`          | number | The initial Y velocity of the projectile.                                |

## Example Usage (Conceptual)

This script is typically called by another entity (e.g., a spell or weapon) that wishes to create a blood tentacle projectile. The `shoot_projectile` function is a utility that handles the actual instantiation and initial velocity setting.

```lua
-- Example of how this script might be triggered (not part of the script itself)
-- local projectile_id = shoot_projectile(
--     EntityLoad("data/entities/projectiles/deck/bloodtentacle.xml"), -- Assuming this loads the entity
--     "data/entities/projectiles/deck/bloodtentacle.xml",
--     player_x,
--     player_y,
--     player_aim_vx,
--     player_aim_vy
-- )
```