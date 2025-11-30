---
title: Base Chain Torch
category: entities
---

# Base Chain Torch

This document describes the `base_chain_torch.xml` entity, which represents a basic, unlit chain torch in Noita. It details the components and key attributes that define its physical properties, appearance, and behavior.

## Core Components

The `base_chain_torch` entity is primarily composed of physics-related components that define its structure, movement, and how it interacts with the game world.

### `PhysicsBody2Component`

This component defines the physical properties of the torch's main body.

*   **`allow_sleep`**: `1` - Allows the physics body to enter a sleep state when inactive to save performance.
*   **`angular_damping`**: `0.01` - A small value for damping rotational movement.
*   **`linear_damping`**: `0.1` - A moderate value for damping linear movement.
*   **`init_offset_x`**: `1.5` - Initial horizontal offset for the physics body.
*   **`root_offset_x`**: `4` - Horizontal offset for the root of the physics body.
*   **`root_offset_y`**: `7` - Vertical offset for the root of the physics body.

### `ExplodeOnDamageComponent`

This component dictates how the entity reacts when damaged. For this specific torch, it's configured to not explode.

*   **`explode_on_death_percent`**: `0` - The entity will not explode upon reaching 0% health.
*   **`explode_on_damage_percent`**: `0` - The entity will not explode when taking damage.
*   **`physics_body_modified_death_probability`**: `1` - If the physics body is modified upon death, there's a 100% chance of this happening.
*   **`physics_body_destruction_required`**: `0.5` - The physics body needs to be at least 50% destroyed for certain death-related effects.
*   **`config_explosion`**: This nested tag contains parameters for explosions. All values are set to `0` or empty strings, indicating no actual explosion effects are triggered by this component.

### `PhysicsImageShapeComponent`

These components define the visual representation and collision shapes of the torch, broken down into segments.

| Attribute     | Value                                    | Description                                                              |
| :------------ | :--------------------------------------- | :----------------------------------------------------------------------- |
| `body_id`     | `0` to `4`                               | Unique identifier for each physics shape.                                |
| `offset_x`    | `0` or `-3.5`                            | Horizontal offset for the sprite.                                        |
| `offset_y`    | `0`, `6`, `12`, `18`, `24`               | Vertical offset for the sprite, creating the chain effect.               |
| `image_file`  | `data/props_gfx/...`                     | Path to the sprite image for each segment.                               |
| `material`    | `metal_chain_nohit` or `metal_nohit`   | Defines the material properties, indicating it cannot be hit directly.   |
| `is_root`     | `1` (for `body_id="4"`)                  | Marks this segment as the root of the chain, typically the torch head.   |

### `PhysicsJoint2Component`

These components connect the different `PhysicsImageShapeComponent` segments, forming the chain structure.

| Attribute     | Value                                       | Description