---
title: Loose Chunks (Huge)
category: entities
---

# Loose Chunks (Huge)

This entity defines a type of loose ground that can break apart into smaller chunks. It's designed for larger, more substantial pieces of terrain.

## Entity Components

### LooseGroundComponent

This component governs the behavior of the loose ground.

*   **`probability`**: `0.2` - The chance this entity will spawn.
*   **`chunk_probability`**: `0.15` - The chance that when this entity breaks, it will form a chunk.
*   **`collapse_images`**: `data/procedural_gfx/collapse_lavabridge/$[0-4].png` - Specifies the image sequence used when the ground collapses.
*   **`chunk_material`**: `rock_box2d` - The material type of the chunks that break off.

### LifetimeComponent

This component determines how long the entity persists.

*   **`lifetime`**: `150` - The base duration the entity exists.
*   **`randomize_lifetime.min`**: `-25` - The minimum random variation for the lifetime.
*   **`randomize_lifetime.max`**: `25` - The maximum random variation for the lifetime.