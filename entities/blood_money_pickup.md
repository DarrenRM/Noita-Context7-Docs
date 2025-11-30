---
title: Blood Money Pickup
category: entities
---

# Blood Money Pickup

This document describes the `bloodmoney_200.xml` entity, which represents a pickup item in Noita. This item is a variation of the gold nugget, specifically designed to represent "blood money."

## Key Components and Attributes

### Entity Definition

*   **name**: `unknown` (This is a placeholder and likely intended to be overridden by the base file or specific game logic.)
*   **tags**: `item_physics`, `gold_nugget` (Indicates it's a physics-based item and a type of gold nugget.)

### Base Entity

*   **file**: `data/entities/items/pickup/goldnugget_200.xml` (Inherits properties from the standard gold nugget pickup.)

### UI Information

*   **UIInfoComponent**:
    *   **name**: `$item_bloodmoney` (The internal identifier for the item's UI display name.)

### Physics and Appearance

*   **PhysicsImageShapeComponent**:
    *   **material**: `bloodgold_box2d` (Specifies the physics material, likely a custom variant of gold for collision and interaction.)

### Item Properties

*   **ItemComponent**:
    *   **_tags**: `enabled_in_world` (Ensures the item is active and interactable when in the game world.)
    *   **item_name**: `$item_bloodmoney_200` (The specific internal name for this variant of blood money.)

### Variable Storage

*   **VariableStorageComponent**:
    *   **name**: `hp_value` (Stores a numerical value related to health or a similar metric.)
    *   **value_float**: `0.6` (The floating-point value associated with `hp_value`. In the context of gold, this might represent a small amount of currency or a fractional value.)