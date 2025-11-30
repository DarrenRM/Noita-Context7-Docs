---
title: Boss Meat Limb Entity
category: entities
---

# Boss Meat Limb Entity

This document describes the `limb.xml` entity, which defines a component part of the "Boss Meat" creature in Noita. It focuses on the visual representation and kinematic properties of a limb.

## Key Components

### SpriteComponent
This entity utilizes multiple `SpriteComponent`s to define the visual appearance of the limb.

*   **`image_file`**: Specifies the sprite asset to be used.
    *   `data/entities/animals/boss_meat/limb_a.xml`
    *   `data/entities/animals/boss_meat/limb_b.xml`
    *   `data/entities/animals/boss_meat/knee.xml`
*   **`offset_x` / `offset_y`**: Adjusts the position of the sprite relative to the entity's origin.
*   **`update_transform` / `update_transform_rotation`**: Set to `0`, indicating that the sprite's transform is not directly updated by the entity's movement.
*   **`z_index`**: Set to `10`, controlling the rendering order of the sprite.

### IKLimbWalkerComponent
This component suggests that the limb is part of an Inverse Kinematics (IK) system designed for walking or locomotion.

### IKLimbComponent
This component defines the kinematic properties of the limb.

*   **`length`**: The length of the limb, set to `80`.

### InheritTransformComponent
This component indicates that the limb inherits transformation properties from its parent entity.