---
title: Necromancer Shop Ragdoll Sprites
category: ragdolls
---

# Necromancer Shop Ragdoll Sprites

This documentation describes the sprite assets used for the Necromancer Shopkeeper's ragdoll in Noita. These files define the visual components of the character's ragdoll when it is active.

## Sprite Components

The following PNG files represent individual parts of the Necromancer Shopkeeper's ragdoll. These are typically used in conjunction with a `.xml` definition file that dictates their positioning and behavior.

### Key Sprites

*   `head.png`: The head sprite for the Necromancer Shopkeeper.
*   `torso.png`: The torso sprite, forming the central part of the ragdoll.
*   `cape.png`: The primary cape sprite.
*   `staff.png`: The sprite for the staff held by the shopkeeper.
*   `arm_right.png`: The right arm sprite.
*   `hand_right.png`: The right hand sprite.

### Cape Variations

The Necromancer Shopkeeper features several variations of its cape, likely for animation or visual flair.

*   `cape1.png`
*   `cape2.png`
*   `cape3.png`
*   `cape4.png`

## Usage

These sprite files are intended to be referenced by a ragdoll definition file (typically a `.xml` file) within the `data/ragdolls/` directory. The `.xml` file will specify how these individual sprites are attached, animated, and interact with physics.

**Example (Conceptual XML Structure):**

```xml
<Ragdoll>
    <Sprite name="head" file="data/ragdolls/necromancer_shop/head.png" />
    <Sprite name="torso" file="data/ragdolls/necromancer_shop/torso.png" />
    <Sprite name="cape" file="data/ragdolls/necromancer_shop/cape.png" />
    <!-- ... other sprites and joint definitions ... -->
</Ragdoll>
```