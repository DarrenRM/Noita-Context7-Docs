---
title: Midas Chunks Entity
category: entities
---

# Midas Chunks Entity

This entity defines the behavior and appearance of "Midas Chunks," which are likely visual elements or debris associated with a Midas-themed effect or area in Noita. It consists of two distinct `LooseGroundComponent` entities, each with inherited transformations, and a `LifetimeComponent` to control their duration.

## Key Components

### LooseGroundComponent

This component dictates how the "chunks" behave as loose ground.

*   **`probability`**: `0.4` - The base probability of this component being active.
*   **`max_distance`**: `160` - The maximum distance from the origin at which this component can affect the ground.
*   **`min_radius`**: `6` - The minimum radius of the ground area affected.
*   **`max_radius`**: `16` - The maximum radius of the ground area affected.
*   **`max_angle`**: `3.1415` - The maximum angle (in radians) for the ground deformation.
*   **`chunk_max_angle`**: `1.57` - The maximum angle for individual chunks.
*   **`chunk_probability`**: `0.15` - The probability of generating individual chunks.
*   **`collapse_images`**: `data/procedural_gfx/collapse_big/$[0-14].png` - Specifies the image sequence used for the collapse animation.

### InheritTransformComponent

This component allows for the transformation (positioning) of child entities relative to their parent.

*   **`position.x`**: Defines the X-coordinate offset.
    *   `-128` for the first chunk.
    *   `128` for the second chunk.
*   **`position.y`**: Defines the Y-coordinate offset.
    *   `0` for both chunks.

### LifetimeComponent

This component controls how long the entity persists.

*   **`lifetime`**: `360` - The base lifetime in frames.
*   **`randomize_lifetime.min`**: `-50` - The minimum randomization for the lifetime.
*   **`randomize_lifetime.max`**: `50` - The maximum randomization for the lifetime.

## Structure

The entity is composed of:

*   Two child `<Entity>` blocks, each containing:
    *   An `<InheritTransformComponent>` to position the chunk.
    *   A `<LooseGroundComponent>` to define its ground-like behavior.
*   A `<LifetimeComponent>` applied to the parent entity, affecting all its children.

This setup suggests two distinct Midas chunks are spawned, positioned symmetrically around the origin, and both behave as loose ground with a limited lifespan.