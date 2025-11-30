---
title: Limb Attacker Perk
category: entities
---

# Limb Attacker Perk

This entity defines a perk that allows the player's limbs to attack enemies.

## Key Components

### IKLimbAttackerComponent
This component enables the limb to act as an attacker.

*   **radius**: The range of the attack.
    *   `50`: The limb can attack enemies within a 50-unit radius.
*   **target_entities_with_tag**: Specifies which entities can be targeted.
    *   `enemy`: Only entities tagged as "enemy" are considered targets.

### IKLimbComponent
This component defines the physical properties of the limb.

*   **length**: The length of the limb.
    *   `50`: The limb has a length of 50 units.

### SpriteComponent
These components define the visual appearance of the limb attacker.

*   **image_file**: The path to the sprite image.
    *   `data/entities/misc/perks/attack_foot/limb_a.png`
    *   `data/entities/misc/perks/attack_foot/limb_B.png`
    *   `data/entities/misc/perks/attack_foot/knee.png`
*   **z_index**: Controls the rendering order of the sprite.
    *   `1.1`: Renders above most other game elements.
*   **offset_x**, **offset_y**: Adjusts the sprite's position relative to its transform.
    *   `0`, `4.5` for limb sprites.
    *   `4`, `4` for the knee sprite.
*   **update_transform**, **update_transform_rotation**: Flags to control if the sprite's transform should be updated by the limb's movement.
    *   `0`: Sprites are static and do not follow limb movement.