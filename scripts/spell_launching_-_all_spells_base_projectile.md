---
title: Spell Launching - All Spells Base Projectile
category: scripts/
---

# Spell Launching - All Spells Base Projectile

This script defines a basic projectile that serves as a foundation for launching other spells in Noita. It utilizes a helper function to spawn a projectile from an existing projectile.

## Key Functionality

The primary purpose of this script is to initiate the spawning of another projectile, specifically `all_spells_base.xml`, from the current entity's position and transform.

### Core Function

*   **`shoot_projectile_from_projectile( entity_id, projectile_file, pos_x, pos_y, velocity_x, velocity_y )`**: This is the central function used. It takes the ID of the entity initiating the shot, the XML file path of the projectile to be spawned, and its initial position and velocity.

## Attributes

While this script is very simple, it relies on the `shoot_projectile_from_projectile` function, which in turn interacts with Noita's entity system. The key elements involved are:

*   **`entity_id`**: The unique identifier of the entity that is currently executing this script. This is obtained using `GetUpdatedEntityID()`.
*   **`pos_x`, `pos_y`**: The X and Y coordinates of the entity's current position. These are retrieved using `EntityGetTransform( entity_id )`.
*   **`"data/entities/projectiles/deck/all_spells_base.xml"`**: This string represents the file path to the projectile definition that will be spawned. This projectile likely contains further logic for how spells are handled.

## Example Usage

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Launches the 'all_spells_base.xml' projectile from the current entity's position.
shoot_projectile_from_projectile( entity_id, "data/entities/projectiles/deck/all_spells_base.xml", pos_x, pos_y, 0, 0 )
```