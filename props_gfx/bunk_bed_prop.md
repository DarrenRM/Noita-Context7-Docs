---
title: Bunk Bed Prop
category: data
---

```

# Bunk Bed Prop

This document describes the `furniture_bunk.xml` entity, which represents a bunk bed prop in Noita. It details its physical properties, visual components, and how its parts are connected.

## Key Attributes

The `Entity` itself has several important tags:

*   **`name="unknown"`**: While the internal name is "unknown", it's identified by its file path.
*   **`serialize="1"`**: Indicates that this entity should be saved and loaded with the game state.
*   **`tags="hittable,teleportable_NOT,prop,prop_physics"`**:
    *   `hittable`: The prop can be damaged or interacted with by projectiles.
    *   `teleportable_NOT`: This prop cannot be teleported.
    *   `prop`: Identifies it as a decorative or interactive prop.
    *   `prop_physics`: Indicates it has physics properties.

## Physics Components

### `PhysicsBody2Component`

This component defines the primary physics body for the bunk bed.

*   **`allow_sleep="1"`**: The physics body can enter a sleep state when not in motion to save performance.
*   **`angular_damping="0.3"`**: Reduces rotational velocity over time.
*   **`linear_damping="0.1"`**: Reduces linear velocity over time.
*   **`init_offset_x="12"`, `init_offset_y="21"`**: Initial offset for the physics body's position.
*   **`kill_entity_after_initialized="1"`**: The entity will be removed after its physics are initialized. This suggests the physics setup is for initial placement or a specific event.

### `PhysicsImageShapeComponent`

These components define the visual and collision shapes of the bunk bed, linked to specific physics bodies.

| Attribute     | Value                               | Description                                                              |
| :------------ | :---------------------------------- | :----------------------------------------------------------------------- |
| `is_root`     | `1`                                 | Marks this as the primary visual component for `body_id="1"`.            |
| `body_id`     | `1`, `2`, `3`, `4`                  | Links the shape to a specific physics body.                              |
| `centered`    | `0`                                 | The image's origin is not centered.                                      |
| `image_file`  | `data/props_gfx/furniture_bunk_bed.png` | The main sprite for the bed.                                             |
| `image_file`  | `data/props_gfx/furniture_bunk_leg_l.png` | Sprite for the left leg.                                                 |
| `image_file`  | `data/props_gfx/furniture_bunk_leg_r.png` | Sprite for the right leg.                                                |
| `material`    | `metal_prop`                        | The material type, affecting interactions and physics.                   |
| `offset_y`    | `-12`                               | Vertical offset for the second bed frame image.                          |
| `z`           | `-1`                                | Determines the drawing layer (lower `z` means further back).             |

## Physics Joints

These components define how different parts of the bunk bed are connected and how they behave when broken.

| Attribute     | `type`           | `break_force` | `body1_id` | `body2_id` | `offset_x` | `offset_y` | Description                                                                                             |
| :------------ | :--------------- | :------------ | :--------- | :--------- | :--------- | :--------- | :------------------------------------------------------------------------------------------------------ |
| Joint 1       | `REVOLUTE_JOINT` | `1.5`         | `1`        | `3`        | `3`        | `17`       | Connects the main body (`1`) to the left leg (`3`) with a revolute joint, allowing rotation.          |
| Joint 2       | `WELD_JOINT`     | `1.25`        | `2`        | `3`        | `3`        | `7`        | Welds the second bed frame part (`2`) to the left leg (`3`).                                            |
| Joint 3       | `WELD_JOINT`     | `1.25`        | `1`        | `4`        | `19`       | `17`       | Welds the main body (`1`) to the right leg (`4`).                                                       |
| Joint 4       | `REVOLUTE_JOINT` | `1.5`         | `2`        | `4`        | `19`       | `7`        | Connects the second bed frame part (`2`) to the right leg (`4`) with a revolute joint, allowing rotation. |

**Note:** The comment `<!-- note the joint types. partially flexible structure after broken -->` indicates that the combination of revolute and weld joints allows the bunk bed to become partially flexible or break apart in a specific way when the `break_force` is exceeded.