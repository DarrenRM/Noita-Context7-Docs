---
title: Limb Walker Perk
category: entities
---

# Limb Walker Perk

This entity defines the "Limb Walker" perk in Noita, which grants the player the ability to walk on their own limbs.

## Core Components

### `IKLimbWalkerComponent`

This is the primary component that enables the limb-walking functionality.

*   **`affect_flying`**: `1` (Boolean) - Indicates whether this perk affects flying entities. In this case, it does.

### `IKLimbComponent`

This component defines the properties of the limbs used for walking.

*   **`length`**: `50` (Float) - The length of the limbs.

## Visuals (`SpriteComponent`)

The perk is visually represented by several sprite components, defining the appearance of the limbs and knees.

### Limb A Sprite

*   **`image_file`**: `data/entities/misc/perks/attack_foot/limb_a.png`
*   **`z_index`**: `1.1`
*   **`offset_x`**: `0`
*   **`offset_y`**: `4.5`
*   **`update_transform`**: `0` (Boolean) - Disables transform updates for this sprite.
*   **`update_transform_rotation`**: `0` (Boolean) - Disables rotation updates for this sprite.

### Limb B Sprite

*   **`image_file`**: `data/entities/misc/perks/attack_foot/limb_B.png`
*   **`z_index`**: `1.1`
*   **`offset_x`**: `0`
*   **`offset_y`**: `4.5`
*   **`update_transform`**: `0` (Boolean)
*   **`update_transform_rotation`**: `0` (Boolean)

### Knee Sprite

*   **`image_file`**: `data/entities/misc/perks/attack_foot/knee.png`
*   **`z_index`**: `1.1`
*   **`offset_x`**: `4`
*   **`offset_y`**: `4`
*   **`update_transform`**: `0` (Boolean)
*   **`update_transform_rotation`**: `0` (Boolean)