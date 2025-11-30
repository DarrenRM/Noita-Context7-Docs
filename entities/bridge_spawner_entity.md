---
title: Bridge Spawner Entity
category: entities
---

# Bridge Spawner Entity

This entity acts as a spawner for creating dynamic, breakable bridges in Noita. It uses raycasting to determine the available space and then procedurally generates a bridge composed of wooden planks and supporting poles.

## Core Functionality

The `do_bridge()` function is the primary logic for this entity. It performs the following key actions:

1.  **Determine Bridge Span:** It uses `raytrace` to find the horizontal extent of a suitable area for the bridge, typically between two surfaces.
2.  **Generate Bridge Components:** Based on the determined span, it procedurally adds various `PhysicsImageShapeComponent` and `PhysicsJoint2Component` entities to form the bridge structure.
3.  **Connect Components:** It uses different joint types (`WELD_JOINT_ATTACH_TO_NEARBY_SURFACE`, `REVOLUTE_JOINT`, `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`) to connect the bridge segments, poles, and supports, defining their breakability.
4.  **Initialize Physics:** Finally, `PhysicsBody2InitFromComponents` is called to bring the generated physics bodies to life.

## Key Attributes and Elements

The `do_bridge()` function dynamically creates components. The most important aspects to consider when modifying or understanding this spawner are:

### Bridge Dimensions and Spacing

*   `overlap`: Controls how much the individual bridge pieces overlap.
*   `piece_width_actual`: The full width of a single bridge plank.
*   `piece_width`: The effective width of a plank after accounting for overlap.
*   `height`: The vertical offset for the top and bottom bridge components.

### Raycasting Parameters

*   `raytrace( x, y, direction, max_length )`: A helper function to perform raycasts.
    *   `direction`: `-1` for left, `1` for right.
    *   `max_length`: The maximum distance to cast the ray.

### Breakability Parameters

These values significantly influence how the bridge will break under stress.

*   `break_force_end`: Break force for joints connecting to the end poles.
*   `break_force_mid`: Break force for joints connecting adjacent bottom planks.
*   `break_force_mid_top`: Break force for joints connecting adjacent top planks.
*   `break_distance`: The distance threshold for joints to break.
*   `break_distance_end`: The distance threshold for joints connecting to end poles.

### Generated Components

The script dynamically adds components. Here are the key types and their roles:

*   **`PhysicsImageShapeComponent`**: Defines the visual and physical shape of bridge elements.
    *   `body_id`: Unique identifier for the physics body.
    *   `offset_x`, `offset_y`: Position relative to the spawner entity.
    *   `image_file`: The sprite used for the component (e.g., `log_vertical`, `plank_horizontal`, `metalrod_vertical`).
    *   `material`: The physical material type (e.g., `wood_prop`, `wood_prop_noplayerhit`).

*   **`PhysicsJoint2Component`**: Connects physics bodies and defines their interaction and breakability.
    *   `type`: The type of joint (e.g., `WELD_JOINT_ATTACH_TO_NEARBY_SURFACE`, `REVOLUTE_JOINT`, `REVOLUTE_JOINT_ATTACH_TO_NEARBY_SURFACE`).
    *   `offset_x`, `offset_y`: Offset for the joint's connection point.
    *   `body1_id`, `body2_id`: The IDs of the bodies being connected.
    *   `break_force`: The force required to break the joint.
    *   `break_distance`: The distance threshold for breaking.
    *   `ray_x`, `ray_y`: Used for `ATTACH_TO_NEARBY_SURFACE` joints to find connection points.

### Example Component Generation (Bottom Plank)

```lua
EntityAddComponent2( entity_id, "PhysicsImageShapeComponent",
{
    body_id = i, -- Unique ID for this plank segment
    offset_x = xpos, -- Horizontal position
    offset_y = 0, -- Vertical position (bottom of the bridge)
    image_file = "data/props_breakable_gfx/plank_horizontal_16_00.png", -- Sprite for the plank
    material = CellFactory_GetType( "wood_prop" ), -- Material type
})

-- Joint connecting this plank to the previous one
EntityAddComponent2( entity_id, "PhysicsJoint2Component",
{
    type = "REVOLUTE_JOINT",
    offset_x = xpos+1, -- Connection point offset
    offset_y = 1,
    body1_id = i-1, -- Previous plank's ID
    body2_id = i, -- Current plank's ID
    break_force = break_force_mid * num_pieces, -- Break force, scaled by number of pieces
    break_distance = break_distance,
})
```

## Modding Considerations

*   **Visuals:** Modify `image_file` paths to use different sprites for planks, poles, or supports.
*   **Materials:** Change `material` types to alter how components interact with the environment or player.
*   **Breakability:** Adjust `break_force` and `break_distance` values to make the bridge more or less durable.
*   **Structure:** Alter `height`, `overlap`, and `piece_width` to change the bridge's dimensions.
*   **New Components:** Add new `EntityAddComponent2` calls to introduce different types of bridge elements or connecting structures.
*   **Spawn Conditions:** This script is designed to be called directly. To control *when* a bridge spawns, you would typically wrap this `do_bridge()` call within another script that triggers based on specific game events or conditions.