---
title: Lukki Limb Minion Entity
category: entities
---

# Lukki Limb Minion Entity

This entity defines a limb component for a "Lukki" creature, specifically a minion variant. It's designed to be part of a larger articulated creature, likely contributing to its movement and appearance.

## Key Components

### `IKLimbWalkerComponent`

This component signifies that the limb is capable of walking or contributing to locomotion.

### `IKLimbComponent`

*   **`length`**: `14` - Defines the physical length of the limb.

### `SpriteComponent`

This entity utilizes two `SpriteComponent`s to render the limb.

*   **Sprite 1:**
    *   **`image_file`**: `data/entities/animals/lukki/lukki_feet/lukki_limb_A_minion.png` - The primary image for this limb segment.
    *   **`z_index`**: `1.1` - Controls the rendering order, placing it above certain other elements.
    *   **`offset_x`**: `0`
    *   **`offset_y`**: `5` - A slight vertical offset for positioning.
    *   **`update_transform`**: `0` - Indicates that the sprite's transform is not automatically updated by the limb's movement.
    *   **`update_transform_rotation`**: `0` - Indicates that the sprite's rotation is not automatically updated by the limb's movement.

*   **Sprite 2:**
    *   **`image_file`**: `data/entities/animals/lukki/lukki_feet/lukki_limb_B_minion.png` - A secondary image for this limb segment, likely for a different part or animation frame.
    *   **`z_index`**: `1.1`
    *   **`offset_x`**: `0`
    *   **`offset_y`**: `5`
    *   **`update_transform`**: `0`
    *   **`update_transform_rotation`**: `0`

## Inheritance

*   **`InheritTransformComponent`**: This component suggests that the entity inherits transformation properties (like position, rotation, scale) from its parent or a controlling entity.