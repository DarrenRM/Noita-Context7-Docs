---
title: Curse Cloud Thunder Status Effect
category: scripts/status_effects
---

# Curse Cloud Thunder Status Effect

This script defines the behavior for a status effect that creates a "curse cloud" which periodically shoots lightning projectiles.

## Key Attributes

*   **Projectile Type:** `data/entities/projectiles/deck/lightning_extra_arcs.xml` - This specifies the type of projectile that will be spawned.
*   **Spawn Offset:** The lightning projectile is spawned with a random horizontal offset (`offset_x` between -32 and 32) and a fixed vertical offset (`pos_y - 32`).
*   **Projectile Velocity:** The projectile is given a significant upward velocity (4000).
*   **Randomization:** The script uses `SetRandomSeed` to ensure varied behavior across different instances and frames.

## Lua Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local pos_x, pos_y = EntityGetTransform( entity_id )

SetRandomSeed( GameGetFrameNum(), pos_x + pos_y + entity_id )

local offset_x = Random( -32, 32 )

shoot_projectile( entity_id, "data/entities/projectiles/deck/lightning_extra_arcs.xml", pos_x + offset_x, pos_y - 32, 0, 4000 )
```