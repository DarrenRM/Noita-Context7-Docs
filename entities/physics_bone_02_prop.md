---
title: Physics Bone 02 Prop
category: entities
---

# Physics Bone 02 Prop

This document describes the `physics_bone_02.xml` entity, a prop in Noita that utilizes physics.

## Entity Definition

The core of this entity is defined by its `name` attribute.

### `name`

*   **unknown**: The internal name for this entity.

## Base Entity

This entity inherits properties from a base entity.

### `Base`

*   **file**: `data/entities/base_item_physics2.xml` - Specifies the base entity file from which this prop derives its physics and item-related functionalities.

## Components

### `PhysicsImageShapeComponent`

This component defines the physical shape and visual representation of the prop using an image.

*   **image_file**: `data/props_gfx/bone_02.png` - The image file used for the prop's visual appearance and collision shape.
*   **material**: `bone_box2d` - The material assigned to this physics object, influencing its interaction with the game world (e.g., friction, density).