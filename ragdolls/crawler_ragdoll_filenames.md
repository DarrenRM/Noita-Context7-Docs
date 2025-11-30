---
title: Crawler Ragdoll Filenames
category: ragdolls
---

```

# Crawler Ragdoll Filenames

This documentation outlines the filenames associated with the "crawler" ragdoll in Noita, as found in the `data/ragdolls/crawler/filenames.txt` file. These files define the visual components of the crawler's ragdoll physics.

## Key Components

The crawler ragdoll is composed of several distinct visual parts, each represented by a PNG image. These images are used by the game engine to simulate the physics and animation of the crawler when it is defeated or interacts with the environment.

### Torso

*   **Filename:** `torso.png`
*   **Description:** This file defines the primary visual representation of the crawler's torso. It is a crucial element for the ragdoll's overall appearance and physics.

## Usage in Modding

When creating mods that alter or replace the crawler's appearance or ragdoll behavior, these filenames are essential for referencing the correct visual assets. Modders can replace these PNG files with their own custom artwork to change how the crawler looks when it ragdolls.

**Example:** A modder could create a `torso.png` with a different texture or shape to give the crawler a unique visual identity upon death.

## Related Files

While this specific file lists the image components, other files within the `data/ragdolls/` directory and potentially within the `data/entities/` directory will reference these ragdoll components to define their behavior and appearance in-game.

---