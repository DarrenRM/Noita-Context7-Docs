---
title: Rock Statue 05
category: entities
---

# Rock Statue 05

This document describes the `statue_rock_05.xml` entity, a decorative rock statue found in Noita.

## Entity Definition

The core of this entity is defined by its `name` attribute, which is currently set to "unknown".

## Base Entity

This statue inherits its fundamental properties from `data/entities/base_item_physics2.xml`. This base file likely provides common physics and collision behaviors for items.

## Components

### Physics Image Shape Component

This component defines the visual representation and physical properties of the statue.

*   **`image_file`**: `data/props_gfx/statues/statue_rock_05.png`
    *   Specifies the graphical asset used for the statue's appearance.
*   **`material`**: `rock_box2d`
    *   Indicates the physical material properties, likely influencing its interaction with the game's physics engine (e.g., density, friction).