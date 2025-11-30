---
title: Teal Slime Tentacle (Thin 01) Entity
category: entities
---

# Teal Slime Tentacle (Thin 01) Entity

This entity defines a thin segment of a teal slime tentacle, utilizing Verlet physics for its flexible movement. It inherits its core properties from a base tentacle piece and is composed of multiple segments.

## Key Components

### `VerletPhysicsComponent`

This component governs the physics simulation of the tentacle segment, allowing it to bend and sway realistically.

*   **`stiffness`**: `1.25` - Controls how rigid the tentacle segments are. Higher values mean less bending.
*   **`num_points`**: `7` - The number of points used to define the Verlet chain, influencing its smoothness and complexity.
*   **`velocity_dampening`**: `0.8` - Reduces the velocity of the tentacle segments over time, causing it to settle.
*   **`resting_distance`**: `1.0` - The preferred distance between adjacent points in the Verlet chain when not under stress.

### `Base` Component

This entity uses multiple `<Base>` components to inherit properties from a common tentacle piece.

*   **`file`**: `data/entities/verlet_chains/tealslime_tentacle/tealslime_tentacle_piece_thin.xml` - Each instance of this base file defines a single segment of the tentacle. The repetition of this tag indicates the tentacle is constructed from multiple such segments.

## Inheritance

This entity primarily relies on inheriting its visual and functional aspects from `tealslime_tentacle_piece_thin.xml`. The `VerletPhysicsComponent` then applies physics to this chain of inherited pieces.

## Usage

This entity is likely used to construct larger, more complex tentacle structures within the game world, providing a flexible and dynamic visual element.