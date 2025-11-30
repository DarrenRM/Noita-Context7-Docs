---
title: Leggy Limb Right Entity
category: entities
---

# Leggy Limb Right Entity

This entity defines a right leg limb for the "Leggy" perk in Noita. It's designed to be a component of a larger walking entity.

## Key Components

### `IKLimbWalkerComponent`

This component enables the limb to function as part of a walking mechanism.

*   `affect_flying`: `1` - Indicates that this limb component affects the entity's flying behavior.

### `IKLimbComponent`

This is the core component for defining a limb's physical properties.

*   `length`: `40` - Specifies the length of the limb.

### `SpriteComponent`

Multiple `SpriteComponent` instances are used to define the visual appearance of the limb.

*   **Primary Limb Sprite:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_a.png` - The main image for the limb.
    *   `z_index`: `1.1` - Controls the rendering order.
    *   `offset_x`, `offset_y`: `0`, `5` - Position offsets for the sprite.
    *   `update_transform`, `update_transform_rotation`: `0`, `0` - Disables automatic transform updates for this sprite.

*   **Right Limb Specific Sprite:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_b_right.png` - The specific image for the right side of the limb.
    *   `z_index`: `1.1`
    *   `offset_x`, `offset_y`: `0`, `5`
    *   `update_transform`, `update_transform_rotation`: `0`, `0`

*   **Knee Sprite:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_knee.png` - The sprite for the knee joint.
    *   `z_index`: `1.1`
    *   `offset_x`, `offset_y`: `4`, `4` - Position offsets for the knee sprite.
    *   `update_transform`, `update_transform_rotation`: `0`, `0`

## Tags

*   `leggy_foot_walker`: This tag likely identifies the entity as a walking foot component for the "Leggy" perk.