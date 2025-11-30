---
title: Big Zombie Ragdoll Filenames
category: ragdolls
---

```

# Big Zombie Ragdoll Filenames

This documentation outlines the filenames associated with the "bigzombie" ragdoll in Noita, as found in the `data/ragdolls/bigzombie/` directory.

## Filenames

The primary file defining the big zombie's ragdoll is:

```
data/ragdolls/bigzombie/empty.png
```

This `.png` file likely contains the visual representation or sprite data for the big zombie's ragdoll.

## Purpose

In Noita modding, ragdoll files are crucial for defining how characters and enemies behave when they die or are affected by physics. They dictate the visual appearance of the detached body parts and their subsequent movement. The `empty.png` in this context suggests a base or default state for the big zombie's ragdoll.

## Key Attributes (Inferred)

While the provided data is minimal, the presence of a ragdoll file implies the following:

*   **Visual Representation:** The `.png` file contains the sprite data for the ragdoll.
*   **Physics Interaction:** This file is linked to the game's physics engine to simulate ragdoll behavior.
*   **Death Animation:** It plays a role in the visual outcome when the big zombie is defeated.
*   **Entity Definition:** It's a component of the "bigzombie" entity's definition within the game's data.

## Further Information

To fully understand the big zombie's ragdoll, one would typically need to examine:

*   The associated `.xml` or `.lua` files that reference this `.png` and define its physics properties, attachment points, and animation states.
*   The `entities/` directory for the `bigzombie.xml` or `bigzombie.lua` file that integrates this ragdoll.