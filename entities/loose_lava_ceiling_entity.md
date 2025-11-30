---
title: Loose Lava Ceiling Entity
category: entities
---

# Loose Lava Ceiling Entity

This entity represents a destructible ceiling segment that can fall and potentially deal damage. It's designed to be part of environmental hazards, particularly in lava-themed areas.

## Key Components

### `LooseGroundComponent`

This component defines the behavior of destructible ground or ceiling elements.

*   **`probability`**: `1.0` - This segment is always present when spawned.
*   **`chunk_probability`**: `1.0` - When destroyed, it will always break into chunks.
*   **`chunk_count`**: `1` - It breaks into a single chunk.
*   **`chunk_max_angle`**: `0` - The chunk does not rotate upon breaking.
*   **`collapse_images`**: `data/procedural_gfx/collapse_lavabridge/small_$[0-4].png` - Specifies the image sequence used for the collapse animation.

### `LifetimeComponent`

This component controls how long the entity exists.

*   **`lifetime`**: `20` - The base lifetime of the entity is 20 frames.
*   **`randomize_lifetime.min`**: `-5` - The lifetime can be reduced by up to 5 frames.
*   **`randomize_lifetime.max`**: `5` - The lifetime can be increased by up to 5 frames.

This means the actual lifetime of an instance of this entity will be between 15 and 25 frames.