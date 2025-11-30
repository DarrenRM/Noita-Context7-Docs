---
title: Sniper Ragdoll Sprites
category: data/ragdolls
---

---

# Sniper Ragdoll Sprites

This documentation outlines the sprite assets used for the "Sniper" ragdoll in Noita. These files define the visual components of the sniper enemy when it is in a ragdoll state.

## Sprite Files

The following PNG files constitute the visual elements of the sniper ragdoll:

*   `torso.png`: The main body segment of the sniper.
*   `head.png`: The head portion of the sniper.
*   `sniper.png`: This likely refers to the primary sprite for the sniper entity itself, potentially used in conjunction with or as a base for the ragdoll parts.
*   `right_thigh.png`: The right thigh segment.
*   `right_foot.png`: The right foot segment.
*   `left_thigh.png`: The left thigh segment.
*   `left_foot.png`: The left foot segment.

## Key Attributes

While the raw data only lists filenames, in the context of Noita modding, these sprites are typically associated with:

### Sprite Sheet Organization

*   **Purpose:** These individual PNGs are often combined into a single sprite sheet for efficient loading and rendering.
*   **Coordinates:** Within the sprite sheet, each part will have defined `x`, `y`, `width`, and `height` coordinates to isolate it.

### Animation and Physics

*   **Ragdoll Physics:** Each sprite component is a distinct physical object that will react to gravity and collisions when the entity is in a ragdoll state.
*   **Attachment Points:** The game engine uses these sprites and their relative positions to reconstruct the ragdoll's pose and movement.

### Modding Considerations

*   **Replacement:** Modders can replace these sprites with custom artwork to change the appearance of the sniper ragdoll.
*   **New Ragdolls:** Understanding this structure allows for the creation of entirely new ragdoll types by defining their own sprite sets and associated physics properties.