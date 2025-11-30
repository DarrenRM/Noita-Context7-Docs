---
title: Barfer Ragdoll Sprites
category: ragdolls
---

---

# Barfer Ragdoll Sprites

This documentation describes the sprite assets used for the "Barfer" enemy's ragdoll. These files define the visual components of the enemy when it is defeated and its body breaks apart.

## Sprite Files

The following PNG files define the individual parts of the Barfer's ragdoll:

*   `head.png`: The head sprite.
*   `upper_torso.png`: The upper body sprite.
*   `lower_torso.png`: The lower body sprite.
*   `left.png`: The left limb sprite.
*   `right.png`: The right limb sprite.

## Usage

These sprites are typically referenced by the game's entity definition files (often in `.xml` format) to construct the ragdoll effect when an entity is destroyed. The game engine will then use these images to visually represent the fragmented body of the Barfer.

## Key Attributes (Conceptual)

While the raw files are just images, in the context of modding, these sprites are associated with:

### 1. Entity Definition
*   **Reference:** How the entity's XML definition points to these sprite files for its ragdoll.
*   **Attachment Points:** The relative positions where each ragdoll part connects to others.

### 2. Physics Simulation
*   **Collision Shapes:** The game engine will likely generate collision shapes for each sprite part to simulate realistic falling and interaction.
*   **Mass/Weight:** Each part might have an assigned mass for physics calculations.

### 3. Visual Properties
*   **Layering:** The order in which sprites are drawn to create a cohesive ragdoll.
*   **Color/Tinting:** Potential for dynamic color changes or effects applied to the sprites.

### 4. Animation (Limited)
*   **Falling Animation:** The natural movement and rotation of each part as it falls.
*   **Impact Reactions:** How sprites might react to collisions with the environment or other entities.