---
title: Physics Chair 1
category: entities
---

# Physics Chair 1

This document describes the `physics_chair_1.xml` entity, a basic physics-enabled prop in Noita.

## Entity Definition

The core of this entity is defined by `data/entities/base_item_physics2.xml`, indicating it inherits physics properties and behaviors from a generic physics item.

## Key Components

### PhysicsImageShapeComponent

This component defines the visual representation and physical properties of the chair.

| Attribute     | Value                     | Description                                     |
|---------------|---------------------------|-------------------------------------------------|
| `image_file`  | `data/props_gfx/chair_1.png` | Specifies the sprite used for the chair.        |
| `material`    | `wood_prop`               | Defines the physical material properties (e.g., hardness, friction). |