---
title: Loose Lavabridge
category: entities
---

# Loose Lavabridge

This entity represents a destructible segment of a lavabridge, commonly found in Noita's environments. When interacted with or damaged, these segments can collapse.

## Key Components

### LooseGroundComponent

This component governs the behavior of destructible ground elements.

*   **`probability`**: `1.0` - Indicates this ground segment is always present and susceptible to collapse.
*   **`chunk_probability`**: `1.0` - The probability that a chunk will break off when the ground collapses.
*   **`chunk_count`**: `1` - The number of chunks that will break off.
*   **`chunk_max_angle`**: `0` - The maximum angle for breaking chunks.
*   **`collapse_images`**: `data/procedural_gfx/collapse_lavabridge/3.png` - Specifies the image used for the collapse effect.

### LifetimeComponent

This component defines how long the entity persists.

*   **`lifetime`**: `20` - The base lifetime of the entity in seconds.
*   **`randomize_lifetime.min`**: `-5` - The minimum randomization applied to the lifetime.
*   **`randomize_lifetime.max`**: `5` - The maximum randomization applied to the lifetime.