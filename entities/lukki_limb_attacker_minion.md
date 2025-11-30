---
title: Lukki Limb Attacker Minion
category: entities
---

# Lukki Limb Attacker Minion

This entity defines a minion limb for the Lukki creature, specifically designed for attacking. It inherits transform properties and utilizes IK (Inverse Kinematics) for limb control.

## Key Components and Attributes

### InheritTransformComponent
*   This component indicates that the entity inherits its transform properties (position, rotation, scale) from its parent.

### IKLimbAttackerComponent
*   **radius**: `14` - Defines the attack radius of this limb.

### IKLimbComponent
*   **length**: `14` - Specifies the length of the IK limb.

### SpriteComponent (x2)
This entity uses two `SpriteComponent`s to render the limb.

*   **Sprite 1:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_A_minion.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0` (Sprite does not update its transform based on parent)
    *   `update_transform_rotation`: `0` (Sprite does not update its rotation based on parent)

*   **Sprite 2:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_B_minion.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`