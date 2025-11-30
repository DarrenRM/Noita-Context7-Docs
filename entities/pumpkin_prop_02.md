---
title: Pumpkin Prop (02)
category: entities
---

---

# Pumpkin Prop (02)

This document describes the `pumpkin_02.xml` entity, a decorative prop in Noita.

## Entity Definition

The core of this entity is defined by `data/entities/base_item_physics2.xml`, indicating it's a physics-enabled item.

### Key Components

*   **`PhysicsImageShapeComponent`**: This component defines the visual and physical properties of the pumpkin.
    *   `image_file`: `data/props_gfx/pumpkin_02.png` - Specifies the graphical asset used for the pumpkin.
    *   `material`: `meat_pumpkin` - Assigns a material to the pumpkin, which can influence its interaction with other game elements (e.g., damage, effects).