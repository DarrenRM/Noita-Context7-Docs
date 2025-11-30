---
title: Furniture Footlocker Entity
category: entities
---

---

# Furniture Footlocker Entity

This document describes the `furniture_footlocker.xml` entity, a basic prop in Noita.

## Entity Definition

The footlocker is defined as an `Entity` with the name "unknown". It inherits its core functionality from `base_item_physics2.xml`.

## Key Components

### Base Item Physics 2

This component provides the fundamental physics properties for the entity.

*   **`init_offset_y`**: `4` - An initial vertical offset applied to the entity upon initialization.
*   **`kill_entity_after_initialized`**: `1` - The entity will be destroyed immediately after its initialization process is complete. This suggests it's a purely visual or temporary element.

### Physics Image Shape

This component defines the visual representation and collision shape of the entity.

*   **`image_file`**: `data/props_gfx/furniture_footlocker.png` - Specifies the image file used for the footlocker's graphics.
*   **`material`**: `metal_prop` - Assigns the "metal\_prop" material, which influences its physical interactions and properties.