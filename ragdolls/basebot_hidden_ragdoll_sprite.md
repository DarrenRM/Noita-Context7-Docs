---
title: Basebot Hidden Ragdoll Sprite
category: ragdolls
---

# Basebot Hidden Ragdoll Sprite

This documentation describes the sprite file used for the hidden ragdoll of the "basebot" entity in Noita.

## Sprite Information

### Filename

The sprite file for the basebot's hidden ragdoll is located at:

```
data/ragdolls/basebot/hidden.png
```

### Purpose

This `.png` file contains the visual representation of the basebot's ragdoll when it is in a "hidden" state. This likely refers to a state where the ragdoll is not actively being rendered or is in a specific animation sequence.

### Key Attributes (Inferred from typical Noita sprite usage)

*   **Format:** PNG (Portable Network Graphics)
*   **Transparency:** Supports alpha channel for transparency.
*   **Dimensions:** The exact dimensions would need to be inspected from the image file itself, but typically these sprites are designed to fit within a specific grid or bounding box for animation.
*   **Usage:** Primarily used by the game engine to render the visual appearance of the basebot's ragdoll in its hidden state.

## AI Modding Considerations

When modding AI behavior or visual aspects related to ragdolls, understanding the sprite files is crucial for:

*   **Animation Sequencing:** Knowing the sprite's appearance can help in defining or modifying animation frames.
*   **Collision/Hitbox Mapping:** While not directly defined in the sprite, the sprite's shape can inform the placement and size of hitboxes for ragdoll physics.
*   **Visual Consistency:** Ensuring new ragdoll states or entities match the visual style of existing ones.

**Note:** This file solely contains the sprite data. Any associated physics, animation logic, or entity definitions would be found in separate `.xml` or `.lua` files.