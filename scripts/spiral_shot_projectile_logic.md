---
title: Spiral Shot Projectile Logic
category: scripts
---

# Spiral Shot Projectile Logic

This script defines the behavior for a projectile that moves in a spiral pattern. It iterates through child entities tagged as "spiral_part" and updates their position based on a stored angle, creating the spiral effect.

## Key Components and Logic

### Entity Initialization and Position
- `entity_id`: Retrieves the unique identifier for the projectile entity.
- `pos_x`, `pos_y`: Stores the initial X and Y coordinates of the projectile.
- `length`: Defines the radius of the spiral.

### Spiral Part Iteration
- The script iterates through all child entities of the projectile.
- It specifically targets children with the tag `"spiral_part"`.

### Angle Management (`theta`)
- For each `"spiral_part"` child, it retrieves a `VariableStorageComponent` named `"theta"`.
- `theta` represents the current angle of the spiral part.
- The angle is incremented by `0.1` in each update, driving the spiral motion.

### Position Update
- The new X and Y coordinates for each spiral part are calculated using trigonometry:
    - `new_x = pos_x + math.cos( theta ) * length`
    - `new_y = pos_y + math.sin( theta ) * length`
- `EntitySetTransform` and `EntityApplyTransform` are used to update the visual position of the spiral part.

### Angle Storage
- The updated `theta` value is stored back into the `VariableStorageComponent` for the next frame's calculation.