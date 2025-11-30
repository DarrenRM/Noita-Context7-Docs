---
title: Furniture Stool Entity
category: entities
---

# Furniture Stool Entity

This document describes the `furniture_stool.xml` entity, which represents a simple stool prop in Noita.

## Entity Definition

The stool is defined as an `Entity` with the name "unknown". It inherits its base properties from `data/entities/base_item_physics2.xml`.

## Key Components

### Base Item Physics 2

This component provides the fundamental physics properties for the stool.

*   **`init_offset_y`**: `4` - An initial vertical offset applied to the entity.
*   **`kill_entity_after_initialized`**: `1` - The entity will be removed from the game shortly after it has been initialized.

### Physics Image Shape

This component defines the visual representation and physical shape of the stool.

*   **`image_file`**: `data/props_gfx/furniture_stool.png` - Specifies the graphical asset used for the stool.
*   **`material`**: `metal_prop` - Assigns a material property to the stool, likely influencing its interaction with other game elements (e.g., damage, friction).