---
title: Glue Anchor Projectile
category: scripts
---

# Glue Anchor Projectile

This script defines the behavior of the "Glue Anchor" projectile in Noita. When fired, it attempts to attach to a surface or a target entity. If it attaches to a surface, it acts as a static anchor. If it attaches to an entity, it attempts to pull that entity towards its origin.

## Key Attributes and Behaviors

### Physics and Attachment

*   **`force`**: A base force value (0.08) used for pulling target entities.
*   **`fall_speed`**: Defines the falling speed of the anchor (3).
*   **Surface Attachment**: If no target entity is found, the anchor attempts to attach to nearby terrain using a `WELD_JOINT_ATTACH_TO_NEARBY_SURFACE`.
    *   `break_force`: The force required to break the weld joint (80).
    *   `break_distance`: The maximum distance for the weld joint (calculated based on `dist * 1.5`).
*   **Entity Attachment**: If a target entity is identified, the anchor attempts to snap to its position.

### Target Interaction

*   **Target Identification**: The script uses a `VariableStorageComponent` to store the `entity_id` of the target. If the target is not alive, it's reset to -1.
*   **Pulling Force**: When attached to an entity, the anchor applies a pulling force towards its parent's position.
    *   **Force Decay**: The pulling force weakens over time, mapped from 1 at `t=0` to 0.25 at `t=300`.
    *   **Pulling Constraints**: The pull is aborted if the distance between the anchor and target is too small (< 8) or too large (> 130), or if the anchor's parent is inside a platform.
*   **Physics Body Check**: The script checks if the target entity has a `PhysicsBodyComponent` or `PhysicsBody2Component`. If not, it proceeds with applying the pulling force.

### Tags and State

*   **`hittable` Tag**: Added to the anchor when `t == 0` (on its first execution), allowing it to be hit by other projectiles.
*   **`glue_anchor` Tag**: Implicitly handled by the script's logic when dealing with other anchors. The script prevents a chain reaction of pulling if the target is another glue anchor and the current anchor is the one being targeted.

### Visuals

*   **`image_file`**: "data/projectiles_gfx/glue_anchor.png" - Specifies the visual asset for the anchor.
*   **`material`**: `CellFactory_GetType("glue")` - Assigns a "glue" material, potentially affecting interactions.

### Internal Logic

*   **`GetUpdatedEntityID()`**: Retrieves the unique identifier for the current entity.
*   **`ComponentGetValue2()`**: Reads the value of a component, specifically `mTimesExecuted` to track the anchor's age.
*   **`EntityAddComponent2()`**: Used to add physics components (`PhysicsBody2Component`, `PhysicsImageShapeComponent`, `PhysicsJoint2Component`).
*   **`EntitySetTransform()`**: Updates the position of the anchor.
*   **`EntityApplyTransform()`**: Applies a transform (movement) to the target entity.
*   **`EntityGetParent()`**: Retrieves the entity that spawned this anchor.
*   **`get_magnitude()`**: Calculates the distance between two points.
*   **`vec_mult()`**: Multiplies a vector by a scalar.
*   **`map()`**: Linearly interpolates a value from one range to another.
*   **`RaytracePlatforms()`**: Checks for collisions with platforms.

```lua
-- Example of how the force is calculated and applied
local age_factor = map(t, 0, 300, 1, 0.25) -- glue pull gets weaker over time
vx, vy = vec_mult(vx, vy, force * age_factor)

EntityApplyTransform(target, target_x + vx, target_y + vy)
```