---
title: Polyorb Death Projectile
category: scripts
---

# Polyorb Death Projectile

This script defines the behavior for a projectile that triggers a polymorph effect upon death.

## Core Functionality

This script is responsible for:
- Loading the `chaos_polymorph.xml` entity at the projectile's current position.
- Immediately killing the projectile entity itself.

## Key Attributes/Elements

The script primarily relies on the `EntityLoad` function to instantiate another entity, which carries the actual polymorph logic. The projectile's own existence is transient.

### `EntityLoad`

- **`"data/entities/projectiles/chaos_polymorph.xml"`**: This is the crucial part. It specifies the entity that will be spawned. This spawned entity is responsible for the visual effects, damage, and the actual polymorph transformation.
- **`pos_x, pos_y`**: The coordinates where the `chaos_polymorph.xml` entity will be created, matching the position of the projectile that triggered this script.

### `EntityKill`

- **`entity_id`**: This function ensures that the projectile entity that executed this script is immediately removed from the game world.

## Example Usage

This script is typically attached to a projectile entity that is designed to have a special "death" effect, such as a projectile that explodes into a polymorph effect.

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

-- Load the entity responsible for the polymorph effect
EntityLoad( "data/entities/projectiles/chaos_polymorph.xml", pos_x, pos_y )

-- Remove the projectile that triggered this script
EntityKill( entity_id )
```