---
title: Furniture Table Entity
category: entities
---

# Furniture Table Entity

This document details the `furniture_table.xml` entity, which represents a destructible table prop in Noita. It focuses on its physical properties and how its components are assembled.

## Entity Definition

The core entity is defined with basic tags:

*   `name`: "unknown" (This is a placeholder and can be customized for modding).
*   `serialize`: "1" (Indicates the entity should be saved and loaded).
*   `tags`: "hittable,teleportable_NOT,prop,prop_physics" (Defines its interaction properties: can be hit, cannot be teleported, is a prop, and has physics).

## Key Components

The table is constructed using several `PhysicsBody2Component` and `PhysicsImageShapeComponent` elements, linked together by `PhysicsJoint2Component` elements.

### PhysicsBody2Component

This component defines the physical properties of the entity.

*   `allow_sleep`: "1" - Allows the physics body to go to sleep when inactive, saving performance.
*   `angular_damping`: "0.3" - Reduces rotational velocity over time.
*   `linear_damping`: "0.1" - Reduces linear velocity over time.
*   `init_offset_x`, `init_offset_y`: "12" - Initial offset for the physics body.
*   `kill_entity_after_initialized`: "1" - The entity will be removed after its physics are initialized.

### PhysicsImageShapeComponent

These components define the visual and physical shape of different parts of the table. Each `PhysicsImageShapeComponent` is linked to a specific `PhysicsBody2Component` via `body_id`.

| Attribute    | Description                                       |
| :----------- | :------------------------------------------------ |
| `is_root`    | "1" - Indicates this is the primary visual part.  |
| `body_id`    | Links the shape to a specific physics body.       |
| `centered`   | "0" - The image is not centered on its origin.    |
| `image_file` | Path to the sprite for this part of the table.    |
| `material`   | "metal_prop" - The material type affecting physics. |
| `z`          | "-1" - Controls the rendering layer (behind other objects). |

**Key Images Used:**

*   `data/props_gfx/furniture_table_top.png`
*   `data/props_gfx/furniture_table_middle.png`
*   `data/props_gfx/furniture_table_leg_l.png`
*   `data/props_gfx/furniture_table_leg_r.png`

### PhysicsJoint2Component

These components define how different parts of the table are connected, simulating its structure.

| Attribute     | Description                                                              |
| :------------ | :----------------------------------------------------------------------- |
| `type`        | The type of joint (e.g., `REVOLUTE_JOINT`, `WELD_JOINT`).                |
| `break_force` | The force required to break the joint.                                   |
| `body1_id`    | The ID of the first physics body involved in the joint.                  |
| `body2_id`    | The ID of the second physics body involved in the joint.                 |
| `offset_x`    | X-axis offset for the joint's connection point.                          |
| `offset_y`    | Y-axis offset for the joint's connection point.                          |

**Joint Configurations:**

*   **Revolute Joints (Legs to Top):** Connects the table legs (`body_id` 2 and 3) to the tabletop (`body_id` 1) allowing for rotation.
*   **Weld Joints (Legs to Middle):** Connects the legs (`body_id` 2 and 3) to the middle support structure (`body_id` 4), effectively welding them in place.

This structure allows the table to be broken apart realistically when subjected to sufficient force.