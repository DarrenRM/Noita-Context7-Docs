---
title: Tentacle Boss Entity
category: entities
---

# Tentacle Boss Entity

This document describes the configuration for a tentacle entity, likely part of a larger boss creature in Noita.

## Core Attributes

*   **`entity_id`**: Dynamically assigned unique identifier for the entity.
*   **`x`, `y`**: The entity's position in the game world.
*   **`a`**: The entity's rotation or angle.

## Behavior

The tentacle's angle (`a`) is dynamically updated based on the game frame number. This creates a subtle oscillating motion.

```lua
local entity_id = GetUpdatedEntityID()
local x, y, a = EntityGetTransform( entity_id )

local arc = 0.2 -- Defines the maximum deviation from the base angle
local angle = GameGetFrameNum() * 0.01 -- Calculates a time-based angle
a = math.cos( angle ) * arc -- Applies a cosine wave to the angle for oscillation

EntitySetTransform( entity_id, x, y, a )
```

**Key Parameters:**

*   **`arc`**: Controls the amplitude of the tentacle's swing.
*   **`GameGetFrameNum() * 0.01`**: The multiplier `0.01` determines the speed of the oscillation.