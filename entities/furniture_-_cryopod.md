---
title: Furniture - Cryopod
category: entities
---

# Furniture - Cryopod

This entity defines a cryopod prop, a piece of furniture found in Noita. It's designed to be a physical object with visual components and basic physics.

## Key Components

### `PhysicsBody2Component`

This component defines the physical properties of the cryopod.

*   **`allow_sleep`**: `1` - Allows the physics body to go to sleep when not in motion, optimizing performance.
*   **`angular_damping`**: `0.3` - Controls how quickly rotational velocity decreases.
*   **`linear_damping`**: `0.1` - Controls how quickly linear velocity decreases.
*   **`init_offset_x`**, **`init_offset_y`**: `8`, `22` - Initial offset for the physics body.
*   **`kill_entity_after_initialized`**: `1` - The entity will be removed from the game world after its physics are initialized. This suggests it's a temporary prop or part of a setup sequence.

### `PhysicsImageShapeComponent`

This component defines the visual representation and collision shape of the cryopod.

*   **`is_root`**: `1` - Indicates this is the primary visual component.
*   **`body_id`**: `1` - Links this shape to `PhysicsBody2Component` with ID 1.
*   **`centered`**: `0` - The image is not centered on its origin.
*   **`image_file`**: `data/props_gfx/furniture_cryopod.png` - The texture file for the main body of the cryopod.
*   **`material`**: `metal_prop_loose` - The material type, influencing physics interactions.

A second `PhysicsImageShapeComponent` is used for the cryopod door:

*   **`body_id`**: `2` - Links this shape to a separate physics body.
*   **`image_file`**: `data/props_gfx/furniture_cryopod_door.png` - The texture file for the door.
*   **`z`**: `-1` - This component is rendered behind the main body.

### `PhysicsJoint2Component`

This component creates a joint between two physics bodies.

*   **`type`**: `WELD_JOINT` - The joint type is a weld, meaning the two bodies are fixed together.
*   **`break_force`**: `1` - The force required to break this joint. A low value suggests it's easily breakable.
*   **`body1_id`**: `1` - Refers to the main cryopod body.
*   **`body2_id`**: `2` - Refers to the cryopod door.
*   **`offset_x`**, **`offset_y`**: `7`, `9` - The offset of the joint relative to the bodies.

## Entity Tags

*   **`hittable`**: The cryopod can be hit by projectiles or other game elements.
*   **`teleportable_NOT`**: The cryopod cannot be teleported.
*   **`prop`**: It is classified as a prop.
*   **`prop_physics`**: It is a prop with physics enabled.