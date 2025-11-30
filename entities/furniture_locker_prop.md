---
title: Furniture Locker Prop
category: entities
---

# Furniture Locker Prop

This document details the `furniture_locker.xml` entity, which represents a prop in Noita. It's designed to be a physics-enabled object with a distinct visual appearance and a functional door.

## Key Attributes

The `Entity` tag defines the core properties of the locker:

*   **`name`**: "unknown" (This is a placeholder and can be customized for specific locker variants).
*   **`serialize`**: "1" (Indicates the entity should be saved and loaded).
*   **`tags`**: "hittable,teleportable_NOT,prop,prop_physics" (Defines its behavior and interactions within the game).

## Components

### `PhysicsBody2Component`

This component defines the physical properties of the locker's main body.

*   **`allow_sleep`**: "1" (Allows the physics body to go to sleep when inactive, optimizing performance).
*   **`angular_damping`**: "0.3" (Reduces rotational velocity over time).
*   **`linear_damping`**: "0.1" (Reduces linear velocity over time).
*   **`init_offset_x`**: "5.5" (Initial horizontal offset for the physics body).
*   **`init_offset_y`**: "25" (Initial vertical offset for the physics body).
*   **`kill_entity_after_initialized`**: "1" (The entity will be removed after its physics are initialized, suggesting it's a static prop).

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape of the locker.

#### Main Frame

*   **`is_root`**: "1" (This is the primary visual component).
*   **`body_id`**: "1" (Links this shape to `PhysicsBody2Component` with ID 1).
*   **`centered`**: "0" (The image is not centered on its origin).
*   **`image_file`**: "data/props_gfx/furniture_locker_frame.png" (The texture for the locker frame).
*   **`material`**: "metal_prop_loose" (The material properties, affecting physics interactions).

#### Door

*   **`body_id`**: "2" (This shape is associated with a separate physics body, implied by the joints).
*   **`centered`**: "0" (The image is not centered on its origin).
*   **`image_file`**: "data/props_gfx/furniture_locker_door.png" (The texture for the locker door).
*   **`material`**: "metal_prop_loose" (The material properties).
*   **`z`**: "-1" (Determines the drawing order, placing the door behind the frame).

### `PhysicsJoint2Component`

These components define the connection between the locker frame and its door, simulating a hinge.

#### Hinge Joint 1

*   **`type`**: "REVOLUTE_JOINT" (Creates a rotational joint).
*   **`break_force`**: "0.75" (The force required to break the joint).
*   **`body1_id`**: "1" (Connected to the locker frame's physics body).
*   **`body2_id`**: "2" (Connected to the locker door's physics body).
*   **`offset_x`**: "8" (Horizontal offset of the joint from `body1_id`'s origin).
*   **`offset_y`**: "6.5" (Vertical offset of the joint from `body1_id`'s origin).

#### Hinge Joint 2

*   **`type`**: "REVOLUTE_JOINT" (Creates a rotational joint).
*   **`break_force`**: "0.75" (The force required to break the joint).
*   **`body1_id`**: "1" (Connected to the locker frame's physics body).
*   **`body2_id`**: "2" (Connected to the locker door's physics body).
*   **`offset_x`**: "8" (Horizontal offset of the joint from `body1_id`'s origin).
*   **`offset_y`**: "18.5" (Vertical offset of the joint from `body1_id`'s origin).

These two joints together create a realistic hinge for the locker door.