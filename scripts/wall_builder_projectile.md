---
title: Wall Builder Projectile
category: scripts
---

# Wall Builder Projectile

This script defines the behavior for a projectile that builds walls. When this projectile is spawned, it immediately creates a `wall_piece` projectile at its current location.

## Key Attributes

*   **`shoot_projectile_from_projectile`**: This is the core function used. It takes the current projectile's entity ID and spawns a new projectile.

### Parameters for `shoot_projectile_from_projectile`

| Parameter          | Type   | Description                                                              |
| :----------------- | :----- | :----------------------------------------------------------------------- |
| `entity_id`        | `int`  | The ID of the projectile entity that is currently active.                |
| `projectile_file`  | `string` | The XML file path to the projectile to be spawned (e.g., `wall_piece.xml`). |
| `pos_x`            | `float`| The X-coordinate where the new projectile will be spawned.               |
| `pos_y`            | `float`| The Y-coordinate where the new projectile will be spawned.               |
| `vel_x`            | `float`| The initial X-velocity of the spawned projectile (set to 0 here).        |
| `vel_y`            | `float`| The initial Y-velocity of the spawned projectile (set to 0 here).        |

## Example Usage

The provided script directly calls `shoot_projectile_from_projectile` with the following arguments:

```lua
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/wall_piece.xml", pos_x, pos_y, 0, 0 )
```

This means that whenever this `wall_builder.lua` script is executed for a projectile, it will spawn a `wall_piece` projectile at the exact same position and with no initial velocity.