---
title: Pumpkin Prop (03)
category: entities
---

# Pumpkin Prop (03)

This document describes the `pumpkin_03.xml` entity, a decorative prop in Noita.

## Entity Definition

The core of this entity is defined by `<Entity name="unknown">`.

## Base Entity

It inherits properties from `data/entities/base_item_physics2.xml`, indicating it's a physics-enabled item.

### Key Components

#### PhysicsImageShapeComponent

This component defines the visual and physical properties of the pumpkin.

*   **`image_file`**: `data/props_gfx/pumpkin_03.png` - Specifies the graphical asset used for the pumpkin.
*   **`material`**: `meat_pumpkin` - Assigns a material type, likely influencing its interaction with other game elements (e.g., damage, physics).