---
title: Tentacle Entity Physics Setup
category: scripts
---

# Tentacle Entity Physics Setup

This script defines the physics bodies and joints for a tentacle-like entity, likely a boss component in Noita. It focuses on creating multiple segments for each tentacle and connecting them to form a chain.

## Key Functions

### `add_tentacles()`

This function is responsible for the entire setup of the tentacle entity's physics.

## Core Components

### Physics Bodies (`PhysicsAddBodyImage`)

The script adds multiple physics bodies, each representing a segment of a tentacle.

| Parameter       | Description                                                              |
| :-------------- | :----------------------------------------------------------------------- |
| `entity_id`     | The unique identifier for the entity being modified.                     |
| `image_path`    | Path to the sprite image for the tentacle segment.                       |
| `material`      | The material type for the physics body (e.g., "meat_slime_green").     |
| `position_x`    | The X-coordinate for the body's placement.                               |
| `position_y`    | The Y-coordinate for the body's placement.                               |

**Key Images Used:**

*   `data/enemies_gfx/slimeboss_tentacle3_0.png`
*   `data/enemies_gfx/slimeboss_tentacle3_1.png`
*   `data/enemies_gfx/slimeboss_tentacle3_2.png`
*   `data/enemies_gfx/slimeboss_tentacle3_3.png`
*   `data/enemies_gfx/tentacle_head.png` (for the head segment)

### Physics Joints (`PhysicsAddJoint`)

These functions connect the physics bodies together, forming the chain-like structure of the tentacles.

| Parameter     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `entity_id`   | The unique identifier for the entity being modified.                     |
| `body_a_id`   | The ID of the first physics body to connect.                             |
| `body_b_id`   | The ID of the second physics body to connect.                            |

The script creates joints to link the head to the first segment, and then each segment to the next, forming a series of connected bodies.

## Physics Body Modifications

### Buoyancy Adjustment

The script iterates through all `PhysicsBodyComponent`s attached to the entity and sets their `buoyancy` property to `"0"`. This likely prevents the tentacle segments from floating or being affected by water.

```lua
	local comp_ids  = EntityGetComponent( entity_id, "PhysicsBodyComponent" )
	if( comp_ids ~= nil ) then
		for index,body in ipairs(comp_ids) do
			ComponentSetValue( body, "buoyancy",  "0" )
		end
	end
```

## Entity Structure

The script appears to create multiple sets of tentacles originating from a central "head" segment (`tentacle_head.png`). Each set consists of several linked segments, arranged in a linear fashion with slight vertical offsets to create a fuller appearance.

**Example of Tentacle Segment Placement (First Set):**

*   `pos_x = 7`, `pos_y = 0`
*   `offset = 11`
*   Segments are placed at `(pos_x, pos_y)`, `(pos_x + offset*1, pos_y)`, `(pos_x + offset*2, pos_y)`, `(pos_x + offset*3, pos_y)`.

Subsequent sets of tentacles are added with different `pos_y` values, creating a layered effect.