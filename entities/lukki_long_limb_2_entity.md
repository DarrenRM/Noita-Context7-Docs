---
title: Lukki Long Limb 2 Entity
category: entities
---

---

# Lukki Long Limb 2 Entity

This entity defines a long limb component for the Lukki creature in Noita. It's primarily used for defining the visual representation and movement mechanics of its legs.

## Key Components

### IKLimbWalkerComponent
This component likely handles the inverse kinematics (IK) and walking behavior for the limb, allowing it to interact with the environment and contribute to the creature's locomotion.

### IKLimbComponent
*   **length**: `80` - Defines the length of the limb. This is a crucial parameter for its visual appearance and how it connects to other body parts.

### SpriteComponent
This entity utilizes multiple `SpriteComponent`s to define the visual appearance of the limb.

*   **Sprite 1 (Main Limb A)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_A_long2.png`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0` (Sprite does not update its transform based on parent)
    *   `update_transform_rotation`: `0` (Sprite does not update its rotation based on parent)

*   **Sprite 2 (Main Limb B)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_limb_B_long2.png`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

*   **Sprite 3 (Knee Joint)**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/lukki_knee2.png`
    *   `offset_x`: `4`
    *   `offset_y`: `4`
    *   `update_transform`: `0`
    *   `update_transform_rotation`: `0`

## Inheritance

### InheritTransformComponent
This component is present but empty, suggesting it might be a placeholder or intended for future use in inheriting transform properties from a parent entity.