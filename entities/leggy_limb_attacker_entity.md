---
title: Leggy Limb Attacker Entity
category: entities
---

# Leggy Limb Attacker Entity

This entity defines a component for a "leggy" limb that can attack. It's designed to be attached to other entities, likely for creature or enemy AI.

## Key Components

### IKLimbAttackerComponent

This component enables the limb to act as an attacker.

| Attribute           | Description                                     |
| :------------------ | :---------------------------------------------- |
| `radius`            | The attack radius of the limb (e.g., 40).       |
| `target_entities_with_tag` | Tags of entities this limb can target (e.g., "enemy"). |

### IKLimbComponent

This component defines the physical properties of the limb.

| Attribute | Description                               |
| :-------- | :---------------------------------------- |
| `length`  | The length of the limb (e.g., 40).        |

### SpriteComponent

This entity utilizes multiple `SpriteComponent`s to define its visual appearance.

| Attribute     | Description