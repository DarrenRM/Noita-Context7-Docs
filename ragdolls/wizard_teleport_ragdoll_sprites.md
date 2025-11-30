---
title: Wizard Teleport Ragdoll Sprites
category: ragdolls
---

---

# Wizard Teleport Ragdoll Sprites

This documentation outlines the sprite assets used for the "Wizard Teleport" ragdoll in Noita. These files define the visual components of the ragdoll when it is in a non-animated, physics-driven state.

## Sprite Files

The following PNG files are used to construct the wizard teleport ragdoll. Each file represents a distinct body part.

| Sprite Name | File Path                               | Description        |
|-------------|-----------------------------------------|--------------------|
| torso       | `data/ragdolls/wizard_tele/torso.png`   | The main body part |
| hand        | `data/ragdolls/wizard_tele/hand.png`    | Hand sprite        |
| feet        | `data/ragdolls/wizard_tele/feet.png`    | Feet sprite        |
| head        | `data/ragdolls/wizard_tele/head.png`    | Head sprite        |

## Usage

These sprite files are referenced by the ragdoll definition for the wizard teleport entity. They are loaded and rendered by the game engine when the entity's ragdoll state is active, typically after death or certain physics interactions.

## Key Attributes (Conceptual)

While the `filenames.txt` only lists the sprite files, the actual ragdoll behavior and appearance are determined by associated configuration files (likely `.xml` or `.lua`) that reference these sprites. Key attributes that would be defined in those files include:

### Physics Properties
*   **Mass:** The weight of each ragdoll part.
*   **Friction:** How much resistance to sliding.
*   **Elasticity:** How bouncy the parts are.
*   **Damping:** How quickly movement slows down.

### Attachment Points
*   **Joints:** How different body parts are connected and their constraints.
*   **Pivot Points:** The center of rotation for each part.

### Collision Shapes
*   **Hitboxes:** The areas that detect collisions.

### Visual Layering
*   **Z-Order:** The order in which sprites are drawn to ensure correct layering.