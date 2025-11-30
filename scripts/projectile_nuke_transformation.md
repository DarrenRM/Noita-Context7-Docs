---
title: Projectile Nuke Transformation
category: scripts/
---

# Projectile Nuke Transformation

This script intercepts existing projectiles and transforms them into "nuke" projectiles, while also disabling their default explosion behavior.

## Core Functionality

The script iterates through all entities tagged as "projectile". For each projectile that does *not* already have the "nuke" tag, it performs the following actions:

1.  **Disables Default Explosions:** It finds `ProjectileComponent`s and sets `on_death_explode` and `on_lifetime_out_explode` to "0", preventing the original projectile from exploding on death or when its lifetime expires.
2.  **Captures Velocity:** It retrieves the current velocity of the projectile using `VelocityComponent`.
3.  **Spawns Nuke Projectile:** It spawns a new projectile from the "nuke" entity definition (`data/entities/projectiles/deck/nuke.xml`) at the original projectile's position and with its captured velocity.
4.  **Kills Original Projectile:** The original projectile is then destroyed.

## Key Components and Attributes

### `ProjectileComponent`

This component is targeted to disable explosion behaviors.

| Attribute               | Description                                                              |
| :---------------------- | :----------------------------------------------------------------------- |
| `on_death_explode`      | Controls if the projectile explodes when it dies. Set to "0" to disable. |
| `on_lifetime_out_explode` | Controls if the projectile explodes when its lifetime expires. Set to "0" to disable. |

### `VelocityComponent`

This component is used to read the projectile's current velocity.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `mVelocity` | The current velocity vector (x, y). |

### `shoot_projectile_from_projectile`

This is a utility function (likely from `utilities.lua`) that spawns a new projectile based on an existing one.

| Parameter        | Description                                                                                             |
| :--------------- | :------------------------------------------------------------------------------------------------------ |
| `projectile_id`  | The ID of the projectile to shoot from (used for position and velocity).                                |
| `entity_file`    | The path to the entity XML file defining the projectile to spawn (e.g., "data/entities/projectiles/deck/nuke.xml"). |
| `pos_x`, `pos_y` | The X and Y coordinates where the new projectile will be spawned.                                       |
| `vel_x`, `vel_y` | The X and Y components of the velocity for the new projectile.                                          |

## Usage

This script is designed to be attached to an entity that will trigger the transformation of other projectiles. It effectively acts as a "nuke converter" for any projectiles that come into its vicinity or are otherwise targeted by its logic.