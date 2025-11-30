---
title: Loose Small Chunks
category: entities
---

---

# Loose Small Chunks

This entity defines small, loose ground chunks that can appear in the game. These chunks are typically generated as part of environmental effects or when certain structures break apart.

## Entity Components

### LooseGroundComponent

This component governs the behavior and appearance of loose ground chunks.

*   **`probability`**: (float) The base probability of this entity spawning.
*   **`chunk_probability`**: (float) The probability that a spawned chunk will actually appear.
*   **`collapse_images`**: (string) A path pattern to the images used for the chunk's collapse animation. The `$[0-14]` indicates a sequence of 15 images.

### LifetimeComponent

This component controls how long the loose chunk persists in the game world.

*   **`lifetime`**: (float) The base duration in seconds the chunk will exist.
*   **`randomize_lifetime.min`**: (float) The minimum amount of time that can be randomly subtracted from the base `lifetime`.
*   **`randomize_lifetime.max`**: (float) The maximum amount of time that can be randomly added to the base `lifetime`.