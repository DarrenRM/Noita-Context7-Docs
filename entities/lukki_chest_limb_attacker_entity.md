---
title: Lukki Chest Limb Attacker Entity
category: entities
---

# Lukki Chest Limb Attacker Entity

This entity defines a component of the Lukki's chest limb, specifically for its attacking behavior. It utilizes several `SpriteComponent`s to define its visual appearance and an `IKLimbAttackerComponent` to manage its attack mechanics.

## Key Components

### IKLimbAttackerComponent

This component governs the attacking capabilities of the limb.

*   **radius**: The radius of the attack.

### IKLimbComponent

This component defines the physical properties of the limb.

*   **length**: The length of the limb.

### SpriteComponent

Multiple `SpriteComponent`s are used to render the different parts of the limb.

*   **image\_file**: Specifies the texture file for the sprite.
*   **z\_index**: Controls the rendering order of the sprite.
*   **offset\_x**: Horizontal offset of the sprite.
*   **offset\_y**: Vertical offset of the sprite.
*   **update\_transform**: Whether the sprite's transform should be updated.
*   **update\_transform\_rotation**: Whether the sprite's rotation should be updated.

## Sprites Used

| Sprite File                                                | Z-Index | Offset X | Offset Y | Update Transform | Update Transform Rotation |
| :--------------------------------------------------------- | :------ | :------- | :------- | :--------------- | :------------------------ |
| `data/entities/animals/lukki/lukki_feet/chest_limb_a.png`  | 1.1     | 0        | 5        | 0                | 0                         |
| `data/entities/animals/lukki/lukki_feet/chest_limb_attacker.png` | 1.1     | 0        | 5        | 0                | 0                         |
| `data/entities/animals/lukki/lukki_feet/chest_elbow.png`   | 1.1     | 4        | 4        | 0                | 0                         |