---
title: Curse Cloud Status Effect Script
category: scripts
---

# Curse Cloud Status Effect Script

This script defines the behavior for the "Curse Cloud" status effect in Noita. It manages the spawning, movement, and lifespan of curse clouds, ensuring that only the most recent cloud persists and that clouds follow their parent entity.

## Key Functionality

### Cloud Persistence and Replacement

The script ensures that when a new curse cloud is spawned, it replaces any older, existing curse clouds associated with the same parent entity. This is achieved by comparing the execution times (`mTimesExecuted`) of the `LuaComponent` attached to each cloud. The youngest cloud is kept, and older ones are killed.

### Initial Positioning

When a curse cloud is first spawned and its position is at the origin (0,0), it will attempt to move to the position of its parent entity. This ensures the cloud starts near the entity that created it.

### Movement Towards Parent

The curse cloud continuously interpolates its position towards the transform of its parent entity. This creates a "following" effect, keeping the cloud in proximity to its source.

## Core Attributes and Logic

| Attribute/Logic | Description |
|---|---|
| `lerp_amount` | A float value (0.993) controlling the interpolation speed for moving the cloud towards its target. Higher values mean faster movement. |
| `GetUpdatedEntityID()` | Retrieves the unique identifier for the current curse cloud entity being processed. |
| `EntityGetTransform()` | Gets the position (x, y) of an entity. |
| `EntityGetRootEntity()` | Retrieves the root entity of a given entity, used here to find the parent entity. |
| `ComponentGetValue2(comp, "mTimesExecuted")` | Retrieves the number of times a specific component (in this case, the `LuaComponent` for the curse cloud script) has been executed. Used for age comparison. |
| `EntityGetAllChildren()` | Returns a list of all direct children of a given entity. Used to find other curse clouds. |
| `EntityHasTag()` | Checks if an entity possesses a specific tag. Used to identify curse clouds. |
| `EntitySetTransform()` | Sets the position and scale of an entity. |
| `EntityKill()` | Destroys an entity. |
| `vec_lerp()` | A utility function for linear interpolation between two 2D vectors. |

## Example Usage (Conceptual)

While this script defines the *behavior* of a curse cloud, its actual *application* would be through another entity or status effect that *applies* this curse cloud effect. For instance, a spell that applies a "Curse" status effect might internally spawn an entity with this `effect_curse_cloud.lua` script attached.

```lua
-- Conceptual example of how a spell might spawn a curse cloud
-- This is NOT part of the provided script, but illustrates its context.

local spell_entity = EntityLoad("data/entities/projectiles/curse_cloud_projectile.xml") -- Assuming a projectile entity that spawns the cloud
local spell_transform = EntityGetTransform(spell_entity)

-- When the spell hits, it might trigger the creation of the curse cloud
-- The curse cloud entity would have a LuaComponent pointing to this script.
local curse_cloud_entity = EntitySpawn("data/entities/status_effects/curse_cloud.xml", spell_transform.x, spell_transform.y)
```