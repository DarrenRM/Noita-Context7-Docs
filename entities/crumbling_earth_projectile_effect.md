---
title: Crumbling Earth Projectile Effect
category: entities
---

# Crumbling Earth Projectile Effect

This entity defines the behavior and visual effects of the "Crumbling Earth" projectile in Noita. It primarily focuses on creating a visual effect of crumbling ground and a magical symbol emitter.

## Key Components

### LoadEntitiesComponent

This component is responsible for loading other entities when this projectile is active.

*   **`entity_file`**: Specifies the XML file for the entity to be loaded. In this case, it's `data/entities/particles/image_emitters/magical_symbol_fast.xml`, which likely handles the visual particle effects.

### Entity (with InheritTransformComponent and LooseGroundComponent)

The core of this projectile's effect is the repeated instantiation of an entity that causes ground to crumble. This is achieved by having three identical `Entity` blocks, each with an `InheritTransformComponent` to position them and a `LooseGroundComponent` to define the crumbling behavior.

#### InheritTransformComponent

This component allows for relative positioning of child entities.

*   **`Transform`**:
    *   **`position.x`**: Offsets the crumbling effect horizontally. The three instances are positioned at -128, 128, and 0, creating a spread effect.
    *   **`position.y`**: Offsets the crumbling effect vertically. All instances are at 0, meaning they are on the same horizontal plane.

#### LooseGroundComponent

This component defines how the ground crumbles.

*   **`probability`**: The chance (0.4 or 40%) that this specific crumbling effect will trigger.
*   **`max_distance`**: The maximum distance (160 pixels) from the projectile's origin that the crumbling effect can occur.
*   **`min_radius`**: The minimum radius (6 pixels) of a crumbling chunk.
*   **`max_radius`**: The maximum radius (16 pixels) of a crumbling chunk.
*   **`max_angle`**: The maximum angle (3.1415 radians, or 180 degrees) around the projectile's origin where crumbling can occur.
*   **`chunk_max_angle`**: The maximum angle (1.57 radians, or 90 degrees) for individual crumbling chunks.
*   **`chunk_probability`**: The probability (0.15 or 15%) that a chunk will be created.
*   **`collapse_images`**: A pattern matching the image files used for the crumbling effect (e.g., `data/procedural_gfx/collapse_big/$[0-14].png`).

### LifetimeComponent

This component determines how long the projectile (and its associated effects) will persist.

*   **`lifetime`**: The base duration of the projectile in frames (360 frames).
*   **`randomize_lifetime.min`**: The minimum amount to subtract from the base lifetime (-50 frames).
*   **`randomize_lifetime.max`**: The maximum amount to add to the base lifetime (50 frames).

This results in a projectile that lasts between 310 and 410 frames, during which it emits a magical symbol and causes ground to crumble in a localized area.