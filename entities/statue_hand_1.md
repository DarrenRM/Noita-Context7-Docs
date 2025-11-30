---
title: Statue Hand 1
category: entities
---

# Statue Hand 1

This document describes the `statue_hand_1.xml` entity, representing a decorative hand statue in Noita.

## Core Components

### PhysicsBody2Component
Manages the physical properties of the statue.
- `angular_damping`: Controls how quickly rotational movement slows down.
- `destroy_body_if_entity_destroyed`: If set to `1`, the physics body is removed when the entity is destroyed.
- `auto_clean`: If set to `0`, the physics body is not automatically cleaned up.

### PhysicsImageShapeComponent
Defines the visual representation and collision shape of the statue.
- `is_root`: Indicates this is the primary visual component.
- `centered`: Centers the image on its origin.
- `image_file`: Specifies the texture file for the statue (`data/buildings_gfx/statue_hand_3.png`).
- `material`: Sets the physical material to `rock_box2d_hard`, influencing its interaction with physics.

### HitboxComponent
Defines the area that can be interacted with or damaged.
- `damage_multiplier`: Reduces incoming damage by 90% (`0.1`).
- `aabb_max_x`, `aabb_max_y`, `aabb_min_x`, `aabb_min_y`: Define the bounding box of the hitbox.

## Lua Components

### LuaComponent (Physics Modified)
This component links to Lua scripts that handle physics-related modifications and interactions.
- `script_physics_body_modified`: Points to `data/scripts/buildings/statue_hand_modified.lua` for physics body modifications.
- `script_kick`: Also points to `data/scripts/buildings/statue_hand_modified.lua`, suggesting this script handles responses to being kicked or hit.
- `execute_every_n_frame`: Set to `-1`, meaning the scripts are not executed on a fixed frame interval by this component.

### LuaComponent (State Management)
This component manages the state and behavior of the statue over time.
- `script_source_file`: Points to `data/scripts/buildings/statue_hand_state.lua` for state management logic.
- `execute_every_n_frame`: Set to `16`, meaning the state script runs every 16 frames.

## Key Attributes Summary

| Component Type          | Key Attributes