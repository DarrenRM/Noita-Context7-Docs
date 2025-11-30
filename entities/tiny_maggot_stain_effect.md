---
title: Tiny Maggot Stain Effect
category: entities
---

---

# Tiny Maggot Stain Effect

This script defines a simple effect that applies dark stains to nearby "mortal" entities when a tiny maggot is present.

## Entity Configuration

This script is designed to be attached to an entity, likely a "tiny maggot" type.

### Key Attributes

*   **`entity_id`**: Dynamically retrieves the ID of the entity the script is attached to.
*   **`x`, `y`**: Retrieves the current position of the entity.
*   **`radius`**: Defines the area of effect for applying stains (set to 40 units).

## Effect Logic

The script iterates through entities within a specified radius and applies a "darkness" stain to them.

### Core Functionality

1.  **`dofile_once("data/scripts/lib/utilities.lua")`**: Includes utility functions.
2.  **`GetUpdatedEntityID()`**: Gets the unique identifier for the current entity.
3.  **`EntityGetTransform(entity_id)`**: Retrieves the position (`x`, `y`) of the entity.
4.  **`EntityGetInRadiusWithTag(x, y, radius, "mortal")`**: Finds all entities within the `radius` that have the "mortal" tag.
5.  **`for i,v in ipairs( t ) do ... end`**: Loops through each "mortal" entity found.
6.  **`EntityAddRandomStains(v, CellFactory_GetType("material_darkness"), 20)`**: Applies random stains to the entity `v`.
    *   **`CellFactory_GetType("material_darkness")`**: Specifies the type of stain to be applied (darkness material).
    *   **`20`**: Represents the intensity or amount of stain to apply.