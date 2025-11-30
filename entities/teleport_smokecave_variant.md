---
title: Teleport (Smokecave Variant)
category: entities
---

# Teleport (Smokecave Variant)

This entity defines a specific instance of a teleport building, likely intended for use within the "Smokecave" area. It inherits its core functionality from a base `teleport.xml` file and customizes its destination.

## Key Attributes

### Base Entity

*   **`file="data/entities/buildings/teleport.xml"`**: Indicates that this teleport inherits its fundamental properties and behaviors from the generic `teleport.xml` entity definition.

### UI Information

*   **`UIInfoComponent`**:
    *   **`name="$teleport_back"`**: This likely sets the in-game name or identifier for this specific teleport, potentially displayed in UI elements. The `$` prefix suggests it's a localization key.

### Teleportation Logic

*   **`TeleportComponent`**:
    *   **`target_x_is_absolute_position="0"`**: This attribute, set to "0" (false), implies that the `target.x` and `target.y` values are *relative* to the teleport's current position, not absolute world coordinates.
    *   **`target.x="1320"`**: The X-coordinate offset for the teleport destination.
    *   **`target.y="-190"`**: The Y-coordinate offset for the teleport destination.

## Summary

This XML file defines a specialized teleport building by extending a base teleport entity. Its primary customization lies in its `TeleportComponent`, which specifies a relative destination point (`1320` units right and `190` units up from its own location). The `UIInfoComponent` suggests a specific in-game name or label for this teleport.