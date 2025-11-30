---
title: Loose Ground Chunks
category: entities
---

# Loose Ground Chunks

This entity defines loose ground chunks that can appear in the game world. These chunks are typically small pieces of terrain that break off and fall.

## LooseGroundComponent

This component governs the behavior of loose ground chunks.

### Key Attributes:

*   **`probability`**: (float) The chance of this entity spawning as a loose chunk.
*   **`chunk_probability`**: (float) The chance of a chunk breaking off from a larger piece of ground.
*   **`collapse_images`**: (string) A path pattern to the images used for the chunk's collapse animation.

## LifetimeComponent

This component controls how long the loose ground chunk will exist before disappearing.

### Key Attributes:

*   **`lifetime`**: (float) The base duration in frames the chunk will exist.
*   **`randomize_lifetime.min`**: (float) The minimum amount to subtract from the base `lifetime`.
*   **`randomize_lifetime.max`**: (float) The maximum amount to add to the base `lifetime`.