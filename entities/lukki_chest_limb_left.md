---
title: Lukki Chest Limb Left
category: entities
---

# Lukki Chest Limb Left

This entity defines the left chest limb for the Lukki creature in Noita. It primarily consists of sprite components that define its visual appearance and an `IKLimbComponent` for its skeletal structure.

## Key Components

### IKLimbWalkerComponent
This component is present but empty, suggesting it's a placeholder or a base component for walking limbs.

### IKLimbComponent
*   **length**: `40` - Defines the length of the limb.

### SpriteComponent
This entity uses multiple `SpriteComponent`s to render different parts of the limb.

*   **Sprite 1 (Base Limb)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_a.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

*   **Sprite 2 (Left Specific)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_b_left.png`
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