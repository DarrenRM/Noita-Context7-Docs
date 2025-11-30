---
title: Disc Bullet Big Damage Projectile
category: scripts
---

# Disc Bullet Big Damage Projectile

This script defines a projectile with a "disc bullet" appearance and a significant damage component.

## Key Components

### Area Damage

This projectile is configured to deal area damage.

*   **`area_damage`**: When enabled, the projectile will apply damage to entities within its radius.

## Script Logic

The script primarily focuses on enabling the area damage component for the entity.

```lua
dofile_once( "data/scripts/lib/utilities.lua" )

local entity_id = GetUpdatedEntityID()

-- Enables the area damage component for this projectile entity.
EntitySetComponentsWithTagEnabled( entity_id, "area_damage", true )
```