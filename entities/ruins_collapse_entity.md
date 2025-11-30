---
title: Ruins Collapse Entity
category: entities
---

# Ruins Collapse Entity

This entity defines the behavior and visual elements associated with the crumbling of ruins in Noita. It's primarily used to create dynamic environmental destruction effects.

## Key Components

### `LooseGroundComponent`

This component governs the mechanics of how the "loose ground" or debris collapses.

*   **`probability`**: `0.4` - The chance this entity will trigger a collapse effect.
*   **`max_distance`**: `100` - The maximum distance from the player at which this collapse can occur.
*   **`min_radius`**: `6` - The minimum radius of the area affected by the collapse.
*   **`max_radius`**: `16` - The maximum radius of the area affected by the collapse.
*   **`max_angle`**: `3.1415` - The maximum angle (in radians) for the overall collapse shape.
*   **`chunk_max_angle`**: `1.57` - The maximum angle for individual debris chunks.
*   **`chunk_probability`**: `0.08` - The probability of individual chunks forming.
*   **`collapse_images`**: `data/procedural_gfx/collapse_big/$[0-14].png` - Specifies the image sequence used for the collapse animation.

### `LifetimeComponent`

This component controls how long the entity, and by extension its effects, will persist.

*   **`lifetime`**: `280` - The base duration (in frames) the entity remains active.
*   **`randomize_lifetime.min`**: `-50` - The minimum random variation to subtract from the base lifetime.
*   **`randomize_lifetime.max`**: `50` - The maximum random variation to add to the base lifetime.