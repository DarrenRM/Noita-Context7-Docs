---
title: Fireball Ray Line Projectile
category: entities
---

# Fireball Ray Line Projectile

This entity defines a projectile that behaves as a continuous ray of fire, likely used for spells that create a line of fire damage.

## Lua Component

The core functionality of this projectile is driven by a Lua script.

### `LuaComponent`

| Attribute           | Value                                     | Description                                                                 |
| :------------------ | :---------------------------------------- | :-------------------------------------------------------------------------- |
| `_enabled`          | `1`                                       | Enables the Lua component.                                                  |
| `script_source_file`| `data/scripts/projectiles/fireball_ray_line.lua` | Specifies the Lua script file that controls the projectile's behavior. |
| `execute_every_n_frame` | `10`                                      | The script will execute its logic every 10 frames.                          |