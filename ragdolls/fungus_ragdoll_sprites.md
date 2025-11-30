---
title: Fungus Ragdoll Sprites
category: ragdolls
---

# Fungus Ragdoll Sprites

This documentation describes the sprite assets used for the "fungus" ragdoll in Noita. These are the visual components that make up the ragdoll's appearance when it is not actively animated.

## Sprite Files

The following `.png` files define the individual parts of the fungus ragdoll.

| Sprite Part     | File Path                               |
|-----------------|-----------------------------------------|
| Torso           | `data/ragdolls/fungus/torso.png`        |
| Cap             | `data/ragdolls/fungus/cap.png`          |
| Left Foot       | `data/ragdolls/fungus/left_foot.png`    |
| Right Foot      | `data/ragdolls/fungus/right_foot.png`   |

## Usage

These sprite files are referenced by the game's ragdoll system to render the visual representation of a fungus entity when it is in a ragdoll state. This typically occurs upon death or when physics interactions cause the entity to lose its standard animation.

## Key Attributes (Conceptual)

While the raw files only contain sprite data, their integration into the game implies the following conceptual attributes for the fungus ragdoll:

*   **Visual Components:** Defines the distinct graphical parts of the ragdoll.
*   **Layering and Z-Ordering:** The order in which these sprites are drawn relative to each other.
*   **Attachment Points:** Implicit points where these sprites connect to form the complete ragdoll.
*   **Physics Interaction:** How these sprites are affected by physics simulations.
*   **Collision Shapes:** Associated collision boundaries for each sprite part.
*   **Material Properties:** Underlying visual properties like color and texture.