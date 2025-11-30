---
title: Leggy Limb Left Entity
category: entities
---

# Leggy Limb Left Entity

This entity defines a left leg component for a "leggy" creature, likely a variant of the Lukki. It utilizes IK (Inverse Kinematics) for limb movement and is composed of multiple sprite components to render its appearance.

## Key Components

### `IKLimbWalkerComponent`

This component enables the limb to function as a walker, contributing to the creature's locomotion.

*   `affect_flying`: Set to `1`, indicating it influences the creature's movement even when airborne.

### `IKLimbComponent`

This is the core component for defining the limb's physical properties.

*   `length`: Set to `40`, defining the length of the limb.

### `SpriteComponent`

Multiple `SpriteComponent` instances are used to define the visual appearance of the leg.

*   **Chest Limb A:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_a.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
*   **Chest Limb B (Left):**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_limb_b_left.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `0`
    *   `offset_y`: `5`
*   **Knee:**
    *   `image_file`: `data/entities/animals/lukki/lukki_feet/chest_knee.png`
    *   `z_index`: `1.1`
    *   `offset_x`: `4`
    *   `offset_y`: `4`

## Tags

*   `leggy_foot_walker`: Indicates this entity is a foot walker component for a "leggy" creature.