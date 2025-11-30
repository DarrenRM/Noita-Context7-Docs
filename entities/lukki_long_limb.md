---
title: Lukki Long Limb
category: entities
---

---

# Lukki Long Limb

This entity defines a long limb component for the Lukki creature in Noita. It primarily handles the visual representation and basic kinematic properties of the limb.

## Key Components

### IKLimbComponent
This component defines the fundamental properties of an Inverse Kinematics (IK) limb.

*   **`length`**: The length of the limb.
    *   Value: `80`

### SpriteComponent
These components define the visual sprites that make up the limb.

*   **Sprite 1 (Limb A)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_A_long.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0` (Sprite does not update its transform based on parent)
    *   `update_transform_rotation`: `0` (Sprite does not update its rotation based on parent)

*   **Sprite 2 (Limb B)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_B_long.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

*   **Sprite 3 (Knee)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_knee.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `4`
    *   `offset_y`: `4`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

### InheritTransformComponent
This component indicates that the entity inherits transform properties from its parent.

### IKLimbWalkerComponent
This component suggests that the limb is intended to be used for walking or locomotion, likely interacting with other IK components to achieve this.