---
title: Boss Limb Entity Definition
category: entities
---

---

# Boss Limb Entity Definition

This document describes the core components and attributes for defining a boss limb entity in Noita, intended for AI-assisted modding.

## Core Components

The `Entity` definition for a boss limb primarily utilizes components to define its visual representation and movement behavior.

### InheritTransformComponent

*   **Purpose:** Inherits transform properties from its parent entity. This is often used for entities that are part of a larger structure.
*   **Key Attributes:**
    *   None explicitly defined in this example, implying default inheritance.

### IKLimbWalkerComponent

*   **Purpose:** Enables the limb to function as a walking limb, likely part of an Inverse Kinematics (IK) system for creature movement.
*   **Key Attributes:**
    *   This component is present but has no explicit attributes defined in this example, suggesting default behavior.

### IKLimbComponent

*   **Purpose:** Defines the physical properties of the limb within an IK system.
*   **Key Attributes:**
    *   `length`: The length of the limb segment.
        *   **Example:** `length="80"`

### SpriteComponent

*   **Purpose:** Defines the visual appearance of the limb, including the image file, offsets, and rendering properties. A boss limb can have multiple sprite components to layer different visual elements.
*   **Key Attributes:**
    *   `image_file`: Path to the sprite image.
        *   **Example:** `image_file="data/entities/animals/boss_limbs/limb1_A.png"`
        *   **Example:** `image_file="data/entities/animals/boss_limbs/limb1_B.png"`
        *   **Example:** `image_file="data/entities/animals/boss_limbs/knee.png"`
    *   `offset_x`: Horizontal offset for the sprite.
        *   **Example:** `offset_x="0"`, `offset_x="3.5"`
    *   `offset_y`: Vertical offset for the sprite.
        *   **Example:** `offset_y="4"`, `offset_y="3.5"`
    *   `update_transform`: Controls whether the sprite's transform updates with the entity.
        *   **Example:** `update_transform="0"` (disabled)
    *   `update_transform_rotation`: Controls whether the sprite's rotation updates with the entity.
        *   **Example:** `update_transform_rotation="0"` (disabled)
    *   `z_index`: Determines the rendering order of the sprite. Higher values are rendered on top.
        *   **Example:** `z_index="10"`