---
title: Platform Wide Collision Entity
category: entities
---

# Platform Wide Collision Entity

This entity defines a static, wide collision platform used in Noita. It's designed to be a non-interactive, solid surface.

## Key Components

### Base Entity

*   **`data/entities/base_item_physics2.xml`**: Inherits physics properties from a base physics entity.

### `PhysicsBody2Component`

This component defines the physical properties of the entity's body.

*   **`kill_entity_after_initialized="0"`**: The entity is not destroyed immediately after initialization.
*   **`is_static="1"`**: The physics body is static, meaning it will not move or be affected by physics forces.
*   **`fixed_rotation="1"`**: The entity's rotation is fixed.
*   **`destroy_body_if_entity_destroyed="1"`**: The physics body will be destroyed if the entity itself is destroyed.

### `PhysicsImageShapeComponent`

This component defines the collision shape using an image.

*   **`centered="1"`**: The image is centered for collision shape generation.
*   **`image_file="data/props_gfx/temporary_platform_wide.png"`**: Specifies the image file used to define the collision shape.
*   **`material="rock_box2d_hard"`**: Assigns a hard rock material to the collision shape, influencing its interaction properties.

### `VelocityComponent`

This component defines the velocity and related properties.

*   **`gravity_y="0"`**: No vertical gravity is applied to this entity.
*   **`air_friction="10"`**: A high air friction value is set, though largely irrelevant for a static entity.
*   **`mass="0.00"`**: The entity has zero mass, consistent with its static nature.

## Tags

*   **`magic_eye_platform_child`**: This tag suggests it might be related to or spawned by a "magic eye" type of entity, possibly for creating temporary platforms.