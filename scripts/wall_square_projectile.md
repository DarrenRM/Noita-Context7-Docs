---
title: Wall Square Projectile
category: scripts
---

# Wall Square Projectile

This script defines the behavior for a projectile that creates a square of wall segments. It spawns multiple "wall_piece" and "wall_builder" entities around its origin.

## Key Attributes

*   **`speed`**: Controls the speed of the spawned "wall_builder" projectiles.
*   **`side`**: Determines the distance from the origin at which the wall segments are spawned, effectively defining the size of the square.

## Core Functionality

The script primarily uses the `shoot_projectile_from_projectile` function to spawn new entities relative to the current projectile's position.

### Spawned Entities

The script spawns the following types of entities:

*   **`data/entities/projectiles/deck/wall_piece.xml`**: These are static wall segments that form the structure.
*   **`data/entities/projectiles/deck/wall_builder.xml`**: These are projectiles that likely have logic to place or construct the wall segments. They are spawned with varying speeds and directions to create the square formation.
*   **`data/entities/projectiles/deck/wall_sound.xml`**: This entity is loaded to play a sound effect associated with the wall creation.

### Spawn Pattern

The script spawns entities in a square pattern, with four distinct points:

1.  **Above**: `pos_y - side`
2.  **Below**: `pos_y + side`
3.  **Left**: `pos_x - side`
4.  **Right**: `pos_x + side`

At each of these points, it spawns one `wall_piece` and two `wall_builder` entities. The `wall_builder` entities are given different velocity components (`speed`, `0-speed`) to create movement in different directions.

## Example Usage (Conceptual)

This script would typically be attached to a projectile entity that, upon impact or activation, triggers this script to execute.

```lua
-- Example of how this script might be triggered by another projectile
-- (This is illustrative and not part of the wall_square.lua script itself)

local entity_id = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)

-- When this projectile hits something, it might trigger the wall square
-- For example, if it has a "Hit" component that calls a script:
-- EntityLoad("data/scripts/projectiles/wall_square.lua", x, y)
```

## Related Files

*   `data/entities/projectiles/deck/wall_piece.xml`
*   `data/entities/projectiles/deck/wall_builder.xml`
*   `data/entities/projectiles/deck/wall_sound.xml`
*   `data/audio/Desktop/projectiles.bank`