---
title: Guts Particle Initialization
category: particles
---

# Guts Particle Initialization

This script initializes the physics properties for "guts" particles, applying random forces and torque to simulate their behavior.

## Key Attributes

### Physics Initialization

*   **`entity_id`**: The unique identifier for the guts particle entity.
*   **`x`, `y`**: The initial position of the particle.
*   **`fx`, `fy`**: Randomly generated forces applied to the particle along the X and Y axes. These values are procedurally generated based on the entity's ID and position to ensure varied behavior.
    *   `fx` range: -2 to 2
    *   `fy` range: -25 to 0
*   **Torque**: A random rotational force applied to the particle. This value is also procedurally generated.
    *   Torque range: -10 to 10

## Code Example

```lua
dofile_once("data/scripts/lib/utilities.lua")

local entity_id    = GetUpdatedEntityID()
local x, y = EntityGetTransform(entity_id)

-- Apply random force
local fx = ProceduralRandomf(entity_id + x, y, -2, 2)
local fy = ProceduralRandomf(x + y, entity_id * 1.532, -25, 0)
PhysicsApplyForce(entity_id, fx, fy)

-- Apply random torque
PhysicsApplyTorque(entity_id, ProceduralRandomf(x + y, entity_id, -10, 10))
```