---
title: Lukki Chest Limb (Right)
category: entities
---

# Lukki Chest Limb (Right)

This entity defines the right chest limb for a Lukki creature in Noita. It primarily consists of sprite components that render the visual appearance of the limb.

## Key Components

### IKLimbWalkerComponent
This component is present but empty, suggesting it's a placeholder or a base component for limb-based movement that might be further defined in other Lukki limb entities.

### IKLimbComponent
*   **length**: `40` - Defines the length of the limb.

### SpriteComponent
This entity utilizes multiple `SpriteComponent`s to construct the visual representation of the limb.

*   **Sprite 1 (Base Limb)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_a.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

*   **Sprite 2 (Right Specific)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_b_right.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

*   **Sprite 3 (Knee Joint)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_knee.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `4`
    *   `offset_y`: `4`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

## Summary of Attributes

| Component           | Attribute              | Value   | Description                                  |
| :------------------ | :--------------------- | :------ | :------------------------------------------- |
| `IKLimbWalkerComponent` | N/A                    | N/A     | Placeholder for limb-based movement.         |
| `IKLimbComponent`   | `length`               | `40`    | Defines the limb's length.                   |
| `SpriteComponent`   | `image_file`           | Varies  | Path to the sprite image.                    |
| `SpriteComponent`   | `z_index`              | `1.1`   | Controls sprite layering.                    |
| `SpriteComponent`   | `offset_x`             | Varies  | Horizontal offset for the sprite.            |
| `SpriteComponent`   | `offset_y`             | Varies  | Vertical offset for the sprite.              |
| `SpriteComponent`   | `update_transform`     | `0`     | Disables automatic transform updates.        |
| `SpriteComponent`   | `update_transform_rotation` | `0`     | Disables automatic rotation updates.         |