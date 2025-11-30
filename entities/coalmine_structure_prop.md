---
title: Coalmine Structure Prop
category: entities
---

# Coalmine Structure Prop

This document describes the `base_coalmine_structure.xml` entity, a prop commonly found in Noita's coalmine environments. It's designed to be a background element with basic physics and a death script.

## Key Components

### PixelSpriteComponent

This component defines the visual representation of the prop.

*   **`image_file`**: `data/props_gfx/coalmine_structure_background_02.png` - Specifies the sprite image used.
*   **`anchor_x`**: `5` - Horizontal anchor point for the sprite.
*   **`anchor_y`**: `49` - Vertical anchor point for the sprite.
*   **`create_box2d_bodies`**: `1` - Enables the creation of Box2D physics bodies for collision.
*   **`clean_overlapping_pixels`**: `1` - Removes overlapping pixels for cleaner rendering.

### SimplePhysicsComponent

This component handles basic physics properties.

*   **`can_go_up`**: `0` - Prevents the entity from moving upwards.

### VelocityComponent

This component is present but has no specific attributes defined, indicating it uses default velocity behavior.

### LuaComponent

This component allows for custom Lua scripting.

*   **`script_death`**: `data/scripts/props/coalmine_structure_death.lua` - Specifies a Lua script to execute when the entity is destroyed.
*   **`execute_on_removed`**: `0` - The death script will not execute if the entity is removed without being destroyed.
*   **`execute_every_n_frame`**: `-1` - The script is not set to execute on a regular frame interval.
*   **`remove_after_executed`**: `0` - The entity will not be automatically removed after the script executes.