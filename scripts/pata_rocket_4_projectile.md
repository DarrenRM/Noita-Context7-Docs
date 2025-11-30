---
title: Pata Rocket 4 Projectile
category: scripts/
---

# Pata Rocket 4 Projectile

This script defines the behavior for the "Pata Rocket 4" projectile in Noita. It primarily focuses on spawning a specific particle effect upon its creation.

## Key Functionality

*   **Entity Loading:** The script's main purpose is to load a pre-defined particle effect entity.

## Core Attributes

*   **`entity_id`**: A unique identifier for the projectile entity.
*   **`pos_x`, `pos_y`**: The X and Y coordinates where the projectile is located.
*   **`eid`**: The entity ID of the spawned particle effect.

## Script Breakdown

```lua
dofile_once("data/scripts/lib/utilities.lua") -- Imports utility functions.

local entity_id    = GetUpdatedEntityID() -- Gets the unique ID of the current projectile entity.
local pos_x, pos_y = EntityGetTransform( entity_id ) -- Retrieves the projectile's position.

-- Loads a particle explosion effect at the projectile's location.
local eid = EntityLoad( "data/entities/particles/particle_explosion/explosion_trail_swirl_pink_slow.xml", pos_x, pos_y )
```